<template>
  <button class="s-button" :class="[(iconPosition === 'right') ? 'icon-right' : '']" @click="$emit('click')">
    <s-icon class="icon" v-if="icon && !loading" :name="icon"></s-icon>
    <s-icon class="icon loading" v-if="loading" name="loading"></s-icon>
    <div class="content">
      <slot></slot>
    </div>
  </button>
</template>
<script>
export default {
  props: {
    icon: {},
    loading: {
      type: Boolean,
      default: false
    },
    iconPosition: {
      type: String,
      default: 'left',
      validator(value) {
        return value === 'left' || value === 'right'
      }
    }
  },
  methods: {

  }
}
</script>
<style lang="scss">
@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

.s-button {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  font-size: var(--font-size);
  height: var(--btn-height);
  padding: 0 1em;
  border-radius: var(--border-radius);
  border: 1px solid var(--border-color);
  background: var(--btn-bg);
  vertical-align: top;

  &:hover {
    border-color: var(--border-color-hover);
  }
  &:active {
    background-color: var(--btn-active-bg);
  }
  &:focus {
    outline: none;
  }

  > .icon {
    order: 1;
    margin-right: 0.1em;
  }
  > .content {
    order: 2;
  }

  &.icon-right {
    > .icon {
      order: 2;
      margin-left: 0.1em;
      margin-right: 0;
    }
    > .content {
      order: 1;
    }
  }
  .loading {
    animation: spin 1.5s infinite linear;
  }
}
</style>
