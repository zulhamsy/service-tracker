<template functional>
  <button
    class="font-semibold rounded focus:outline-none"
    :class="[props.color, props.size, data.staticClass]"
    v-on="listeners"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'custom-button',
  functional: true,
  props: {
    color: {
      type: String,
      required: false
    },
    size: {
      type: String,
      default: 'lg'
    }
  }
}
</script>

<style scoped>
.lg {
  @apply py-2 px-6 text-lg;
}

.md {
  @apply py-2 px-4 text-base;
}

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

button:disabled {
  @apply bg-gray-300 text-white border-0;
  @apply hover:bg-gray-300 hover:text-white;
  @apply cursor-default;
}
</style>
