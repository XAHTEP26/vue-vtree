<script>
  export default {
    name: 'VTree',
    render() {
      if (!this.$scopedSlots.default) this.$scopedSlots = this.$parent.$scopedSlots
      return this.$scopedSlots.default ? this.$scopedSlots.default(this.scopeData) : null
    },
    props: ['scope-data'],
  }
</script>
