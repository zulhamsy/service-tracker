<template>
  <div class="p-2">
    <base-btn :color="color" @click="logHello" class="mb-3">Cancel</base-btn>
    <base-input
      placeholder="Username"
      class="block"
      v-model="text"
    ></base-input>
  </div>
</template>

<script>
import BaseButton from '@/components/BaseButton'
import BaseInput from '@/components/BaseInput'
export default {
  components: {
    'base-btn': BaseButton,
    'base-input': BaseInput
  },
  data() {
    return {
      color: 'primary',
      text: ''
    }
  },
  methods: {
    logHello() {
      console.log('Hello from Btn Components')
    }
  }
}
</script>
<style></style>
