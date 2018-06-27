<template>
  <button class="s-button" :class="[(iconPosition === 'right') ? 'icon-right' : '']">
    <svg v-if="icon" class="icon">
      <use :xlink:href="`#s-${icon}`"></use>
    </svg>
    <div class="content">
      <slot></slot>
    </div>
  </button>
</template>
<script>
export default {
  props: ['icon', 'iconPosition']
}
</script>
<style lang="scss">
  .s-button{ 
    display: inline-flex;
    justify-content: center;
    align-items: center;
    font-size: var(--font-size);
    height: var(--btn-height);
    padding: 0 1em;
    border-radius: var(--border-radius);
    border: 1px solid var(--border-color);
    background:var(--btn-bg);
    vertical-align: top;
    
    &:hover{
    border-color: var(--border-color-hover);
    }
    &:active{
      background-color: var(--btn-active-bg);
    }
    &:focus{
      outline: none;
    }

    > .icon{
      order: 1;
      margin-right: .1em;
    }
    > .content{
      order: 2;
    }

    &.icon-right{
      >.icon{
        order: 2;
        margin-left: .1em;
        margin-right: 0;
      }
      >.content{
       order: 1;
      }
    }
  }
  
</style>
