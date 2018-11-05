<template>
  <div
    :class="{'_active': show}"
    class="ModalMask"
  ></div>
</template>

<script>
export default {
  name: "ModalMask",
  props: {
    show: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped lang="scss">
.ModalMask {
  width: 100%;
  height: 100vh;
  background: rgba(0, 0, 0, 0.2);
  visibility: hidden;
  opacity: 0;
  transition: 0.12s ease-in;
  cursor: pointer;
  &._active {
    visibility: visible;
    opacity: 1;
  }
}
</style>
