<template>
  <div
    :class="{'_active': show}"
    class="AppModal"
  >
    <modal-mask
      class="AppModal_Mask"
      :show="maskShow"
      @click.native="clickModalMask"
    ></modal-mask>
    <Modal-content
      class="AppModal_Content"
      :style="styleObject"
      @on-scroll-modal-content="scrollModalContent"
      @on-click-modal-close="onClickModalClose"
    ></Modal-content>
  </div>
</template>

<script>
import ModalMask from "../atoms/ModalMask"
import ModalContent from "../atoms/ModalContent"
export default {
  name: "AppModal",
  components: {ModalContent, ModalMask},
  props: {
    show: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      maskShow: false,
      modalContentHeight: null
    }
  },
  computed: {
    styleObject() {
      return {
        height: this.modalContentHeight + 'px',
        bottom: this.maskShow ? '0px' : '-200px'
      }
    }
  },
  mounted() {
    this.modalContentHeight = window.innerHeight
  },
  methods: {
    scrollModalContent(flag) {
      this.maskShow = flag
    },
    clickModalMask() {
      this.maskShow = false
      document.querySelector('.ModalContent').scrollTop = 0
    },
    onClickModalClose() {
      this.$emit('on-click-modal-close')
      document.querySelector('.ModalContent').scrollTop = 0
    }
  }
}
</script>

<style scoped lang="scss">
.AppModal {
  position: fixed;
  max-width: 500px;
  width: 100%;
  height: 100vh;
  top: 0;
  transform: translateY(100%);
  transition: 0.12s ease-out;
  -webkit-overflow-scrolling: touch;
  &._active {
    transform: translateY(0%);
  }
  &_Mask {
    position: absolute;
    top: 0;
    left: 0;
  }
  &_Content {
    position: absolute;
    bottom: 0;
    left: 0;
    transition: 0.12s ease-out;
  }
}
</style>
