<template>
  <form>
    <base-input
      placeholder="Distance in KM"
      type="number"
      v-model.number="distance"
      class="block w-2/3"
    />
    <date-picker
      v-model="time"
      value-type="DD/MM/YYYY"
      :disabled-date="disabledDate"
      class="block w-2/3"
    >
      <template v-slot:input>
        <base-input :value="time" class="flex w-full" placeholder="Date" />
      </template>
    </date-picker>
    <base-button color="primary" size="md" type="submit"
      >Submit Ride</base-button
    >
  </form>
</template>

<script>
import DatePicker from 'vue2-datepicker'
import 'vue2-datepicker/index.css'
export default {
  name: 'submit-distance',
  components: { DatePicker },
  data() {
    return {
      time: null,
      distance: null
    }
  },
  methods: {
    disabledDate(date) {
      return date > new Date()
    }
  }
}
</script>

<style scoped></style>
