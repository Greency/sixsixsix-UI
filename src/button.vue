<template>
  <button class="s-button">按钮</button>
</template>
<script>
export default {
  
}
</script>
<style lang="scss">
  .s-button{
    font-size: var(--font-size);
    height: var(--btn-height);
    padding: 0 1em;
    border-radius: var(--border-radius);
    border: 1px solid var(--border-color);
    background:var(--btn-bg);
    
    &:hover{
    border-color: var(--border-color-hover);
    }
    &:active{
      background-color: var(--btn-active-bg);
    }
    &:focus{
      outline: none;
    }
  }
  
</style>
