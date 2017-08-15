<template>
  <div v-if="isOpen">
    Hello world!
    <button @click="toggleIsOpen">Close from Inside Child!</button>
    <slot name="content"></slot>
  </div>
</template>

<script>
export default {
  name: 'child',
  methods: {
    toggleIsOpen() {
      this.$emit('toggled',false)
    }
  },
  props: {
    isOpen: {
      type: Boolean,
      default: false
    }
  }
}
</script>
