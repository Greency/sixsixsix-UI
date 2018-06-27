<template>
  <div class="s-button-group">
    <slot></slot>
  </div>
</template>
<script>
export default {
  mounted(){
    for(let node of this.$el.children){
      if(node.nodeName !== 'BUTTON'){
        console.warn('s-button-group的子元素必须是s-button')
      }
    }
  }
}
</script>
<style lang="scss">
  .s-button-group{
    display: inline-flex;
    vertical-align: top;

    > .s-button{
      border-radius: 0;
      &:not(:first-child){
        margin-left: -1px;
      }
      &:first-child{
        border-top-left-radius: var(--border-radius);
        border-bottom-left-radius: var(--border-radius);
      }
      &:last-child{
        border-top-right-radius: var(--border-radius);
        border-bottom-right-radius: var(--border-radius);
      }
      &:hover{
        position: relative;
        z-index: 1;
      }
    }
  }
</style>
