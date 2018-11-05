<template>
  <div class="AppMain">
    <app-button
      class="AppMain_Buuton"
      @click.native="onClickModalOpen"
    >Modal</app-button>
  </div>
</template>

<script>
import AppButton from "../atoms/AppButton/Default"
export default {
  name: "AppMain",
  components: {AppButton},
  methods: {
    onClickModalOpen() {
      this.$emit('on-click-modal-open')
    }
  }
}
</script>

<style scoped lang="scss">
.AppMain {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}
</style>
