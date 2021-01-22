<template>
  <div class="p-2">
    <base-btn :color="color" @click="logHello" class="mb-3">Cancel</base-btn>
    <base-input
      placeholder="Username"
      class="block mb-3"
      v-model="text"
    ></base-input>
    <tab-wrapper>
      <tab-child title="Menu 1">Sebuah Konten</tab-child>
      <tab-child title="Menu 2">Konten Kedua</tab-child>
      <tab-child title="Menu Baru">Konten Ketiga</tab-child>
    </tab-wrapper>
  </div>
</template>

<script>
import BaseButton from '@/components/BaseButton'
import BaseInput from '@/components/BaseInput'
import TabWrapper from '@/components/BaseTabWrapper'
import TabChild from '@/components/BaseTabChild'
export default {
  components: {
    'base-btn': BaseButton,
    'base-input': BaseInput,
    'tab-wrapper': TabWrapper,
    'tab-child': TabChild
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
