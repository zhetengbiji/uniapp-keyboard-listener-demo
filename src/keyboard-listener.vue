<template>
  <view></view>
</template>

<script>
export default {
  methods: {
    onEvent(event) {
      this.$emit(event.type, event)
    },
  },
}
</script>

<script module="keyboard" lang="renderjs">
export default {
  mounted () {
    const onKey = (event) => {
      const keys1 = ['type', 'timeStamp']
      const keys2 = ['altKey', 'code', 'ctrlKey', 'isComposing', 'key', 'location', 'metaKey', 'repeat', 'shiftKey']
      const keys3 = ['char', 'charCode', 'keyCode', 'keyIdentifier', 'keyLocation', 'which']
      const data = {}
      keys1.concat(keys2, keys3).forEach(key => data[key] = event[key])
      this.$ownerInstance.callMethod('onEvent', data)
    }
    const names = ['keydown', 'keyup']
    names.forEach(name => {
      document.addEventListener(name, onKey, false)
    })
    this.$on('hook:beforeDestroy', () => {
      names.forEach(name => {
        document.removeEventListener(name, onKey, false)
      })
    })
  }
}
</script>

<style>
</style>
