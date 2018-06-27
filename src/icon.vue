<template>
  <svg class="icon">
    <use :xlink:href="`#s-${name}`"></use>
  </svg>
</template>
<script>
export default {
  props: {
    name: {
      type: String
    }
  }
}
</script>
<style lang="scss">
  .s-icon{
    width: 1rem;
    height: 1rem;
  }
</style>
