<template>
  <div class="grid-container">
    <div class="input">
      <p>Submit Your Ride!</p>
      <distance-input />
    </div>
    <div class="statistic">
      <p>this section is under construction</p>
    </div>
    <div class="latest">
      <p>this section is also under construction</p>
    </div>
  </div>
</template>

<script>
import SubmitDistance from '@/components/SubmitDistance'
export default {
  components: {
    'distance-input': SubmitDistance
  }
}
</script>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: repeat(2, 1fr);
  gap: 0.5em;
  grid-template-areas:
    'input latest'
    'statistic statistic';
  @apply container mx-auto;
}
.statistic {
  grid-area: statistic;
}
.latest {
  grid-area: latest;
  @apply shadow py-3 px-5 bg-gray-50;
}
.input {
  grid-area: input;
  @apply shadow py-3 px-5;
}
.input p {
  @apply font-semibold text-lg mb-3;
}
</style>
