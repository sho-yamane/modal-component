<template>
  <button class="AppButton" :class="className" type="button">
    <slot>text</slot>
  </button>
</template>

<script>
import Presenter from './Presenter.vue'
export default {
  name: 'AppButton',
  extends: Presenter,
  props: {
    ...Presenter.props
  }
}
</script>

<style scoped lang="scss">
@import './style.scss';
</style>
