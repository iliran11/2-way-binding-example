<template>
  <div>
    <button @click="toggleChild">Close Child from Parent (not from a passed slot)</button>
    <child :isOpen="isOpen"
      @toggled="toggleChild">
      <button slot="content"
        @click="toggleChild"> Close Child from Parent's Slot!</button>
    </child>
  </div>
</template>

<script>
import child from './child.vue'
export default {
  name: 'parent',
  components: { child },
  data() {
    return {
      isOpen: true
    }
  },
  methods: {
    toggleChild() {
      this.isOpen = !this.isOpen
    }
  }
}
</script>
