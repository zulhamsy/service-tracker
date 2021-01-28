<template>
  <div>
    <!-- Child Title -->
    <ul>
      <li
        v-for="(tab, index) in tabs"
        :key="index"
        :class="{ active: index == selectedTab }"
        @click="selectTab(index)"
      >
        {{ tab.title }}
      </li>
    </ul>
    <!-- Child Component -->
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'tab-wrapper',
  data() {
    return {
      tabs: [],
      selectedTab: ''
    }
  },
  methods: {
    selectTab(i) {
      this.selectedTab = i
      this.tabs.forEach((tab, index) => {
        tab.active = index == i
      })
    }
  },
  created() {
    this.tabs = this.$children
  },
  mounted() {
    this.selectTab(0)
  }
}
</script>

<style scoped>
ul {
  @apply flex;
  @apply md:w-2/3;
}

li {
  @apply flex-1;
  @apply px-4 py-3 text-gray-500 cursor-pointer text-center;
  @apply hover:bg-blue-50;
}

.active {
  @apply font-semibold text-blue-600;
  @apply border-b-2 border-blue-600;
}
</style>
