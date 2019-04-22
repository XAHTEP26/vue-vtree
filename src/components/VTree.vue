<script>
export default {
  name: 'VTree',
  provide() {
    return { parentVTree: this }
  },
  inject: {
    parentVTree: { default: undefined }
  },
  render() {
    if (!this.$scopedSlots.default && this.parentVTree) this.$scopedSlots = this.parentVTree.$scopedSlots;
    return this.$scopedSlots.default ? this.$scopedSlots.default(this.scopeData) : null;
  },
  props: ['scope-data'],
}
</script>
