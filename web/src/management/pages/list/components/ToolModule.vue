<template>
  <div class="tool-root" @click.stop="onClick">
    <span class="tool-root-btn-text" :style="{ width: width + 'px' }">{{ label }}</span>
  </div>
</template>

<script>
export default {
  name: 'ToolModule',
  props: {
    value: String,
    label: String,
    type: String,
    width: Number
  },
  methods: {
    onClick() {
      this.$emit('call', {
        key: this.value,
        name: this.label
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.tool-root {
  display: inline-block;
  font-size: 0;
  line-height: 0;
  flex: 1;
  .icon-list-more {
    color: $primary-color;
    font-size: 20px;
    position: relative;
    top: 3px;
  }
  span {
    font-size: 14px;
    color: $primary-color;
    display: inline-block;
    text-align: center;
    line-height: 16px;
    cursor: pointer;
  }
}
</style>
