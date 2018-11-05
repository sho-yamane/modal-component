<script>
export default {
  name: 'Presenter',
  props: {
    tag: {
      type: String,
      default: 'p',
      required: false,
      validator(val) {
        return ['div', 'p', 'span'].includes(val)
      }
    }
  }
}
</script>
