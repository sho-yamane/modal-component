<template>
  <component
    :is="tag"
    class="AppText"
  >
    <slot>text</slot>
  </component>
</template>

<script>
import Presenter from './Presenter.vue'
export default {
  name: 'AppText',
  extends: Presenter,
  props: {
    ...Presenter.props
  }
}
</script>

<style scoped lang="scss">
@import './style.scss';
</style>
