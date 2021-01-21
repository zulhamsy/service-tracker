<template functional>
  <input
    :type="props.type"
    v-bind="data.attrs"
    :class="[props.color, data.staticClass]"
    @input="listeners.input($event.target.value)"
  />
</template>

<script>
export default {
  name: 'CustomInput',
  functional: true,
  inheritAttrs: true,
  props: {
    color: {
      type: String,
      default: 'primary'
    },
    type: {
      type: String,
      default: 'text'
    }
  }
}
</script>

<style scoped>
input {
  @apply rounded border border-gray-300 border-l-4;
  @apply py-3 px-2 mb-3;
  @apply focus:outline-none focus:ring-1;
}

.primary {
  @apply focus:border-blue-500 focus:ring-blue-500;
}
</style>
