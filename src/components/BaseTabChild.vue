<template>
  <div v-if="active">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'tab-child',
  props: {
    title: {
      type: String,
      default: 'Unnamed Menu'
    }
  },
  data() {
    return {
      active: false
    }
  }
}
</script>

<style scoped></style>
