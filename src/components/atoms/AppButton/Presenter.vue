<script>
export default {
  name: 'Presenter',
  props: {
    size: {
      type: String,
      default: 'm'
    },
    circle: {
      type: Boolean,
      default: false
    }
  },
  computed: {
    className() {
      const className = []

      if (this.size) {
        className.push(`_${this.size}`)
      }

      if (this.circle) {
        className.push('_circle')
      }

      return className
    }
  }
}
</script>
