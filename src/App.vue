<template>
  <div class="p-2">
    <distance-sub class="mb-7" />
    <vue-ellipse-progress
      :progress="progress"
      size="150"
      legend="false"
      :color="colorStroke"
    >
      <template v-slot:legend-caption>
        <span class="font-semibold">Servis Berkala</span>
      </template>
      <template v-slot:default>
        <span class="text-sm">250 KM Remaining</span>
      </template>
    </vue-ellipse-progress>
  </div>
</template>

<script>
import SubmitDistance from '@/components/SubmitDistance'
export default {
  components: {
    'distance-sub': SubmitDistance
  },
  data() {
    return {
      gradient: {
        radial: false,
        colors: [
          { color: '#3B82F6', offset: 0, opacity: 1 },
          { color: '#EF4444', offset: 100, opacity: 1 }
        ]
      },
      progress: 96
    }
  },
  computed: {
    colorStroke() {
      if (this.progress <= 25) return '#059669'
      if (this.progress <= 50) return '#2563EB'
      if (this.progress <= 90) {
        return '#D97706'
      } else {
        return '#DC2626'
      }
    }
  }
}
</script>

<style scoped></style>
