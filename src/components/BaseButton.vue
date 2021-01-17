<template>
  <button
    class="py-2 px-6 font-semibold rounded focus:outline-none text-lg"
    :class="disabledClass || color"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    color: {
      type: String,
      required: false
    }
  },
  computed: {
    disabledClass() {
      if (this.$attrs.disabled != undefined) {
        return 'disabled'
      } else {
        return false
      }
    }
  }
}
</script>

<style scoped>
.primary {
  @apply bg-blue-600 text-white;
  @apply hover:bg-blue-700;
  @apply focus:ring focus:ring-blue-500 focus:ring-offset-0;
}

.success {
  @apply bg-green-600 text-white;
  @apply hover:bg-green-700;
  @apply focus:ring focus:ring-green-500 focus:ring-offset-0;
}

.danger {
  @apply bg-red-600 text-white;
  @apply hover:bg-red-700;
  @apply focus:ring focus:ring-red-500 focus:ring-offset-0;
}

.outline-danger {
  @apply border border-red-300 text-red-400;
  @apply hover:bg-red-400 hover:text-white;
  @apply focus:ring focus:ring-red-500 focus:ring-offset-0 focus:text-red-600;
}

.outline-gray {
  @apply border border-gray-300 text-gray-400;
  @apply hover:bg-gray-400 hover:text-white;
  @apply focus:ring focus:ring-gray-500 focus:ring-offset-0 focus:text-gray-600;
}

.disabled {
  @apply bg-gray-300 text-white;
  @apply cursor-default;
}
</style>
