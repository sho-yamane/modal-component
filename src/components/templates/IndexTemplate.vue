<template>
  <div class="IndexTemplate">
    <app-main
      @on-click-modal-open="clickModalOpen"
    ></app-main>
    <app-modal
      :show="modalShow"
      @on-click-modal-close="clickModalClose"
    ></app-modal>
  </div>
</template>

<script>
import AppMain from "../organisms/AppMain"
import AppModal from "../organisms/AppModal"
export default {
  name: "IndexTemplate",
  components: {AppModal, AppMain},
  data() {
    return {
      modalShow: false
    }
  },
  methods: {
    clickModalOpen() {
      this.modalShow = true
    },
    clickModalClose() {
      this.modalShow = false
    }
  }
}
</script>

<style scoped>

</style>
