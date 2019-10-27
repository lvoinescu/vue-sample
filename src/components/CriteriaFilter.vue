<template>
  <div>
    <p>Date picker</p>
    <p>{{dynamicText}}</p>
    <datepicker name="startDate" @selected="updateStartDate"></datepicker>
    <datepicker name="endDate" @selected="updateEndDate"></datepicker>
  </div>
</template>

<script>
import Datepicker from "vuejs-datepicker";

export default {
  props: ["dynamicText"],
  components: {
    Datepicker
  },
  data() {
    return {
      startDate: null,
      endDate: null
    };
  },
  computed: {
    criteria: function() {
      return { startDate: this.startDate, endDate: this.endDate };
    }
  },
  methods: {
    updateFilter() {
      console.log("Log in filter :" );

      this.$emit("filterChanged", {
        startDate: this.startDate,
        endDate: this.endDate
      });
    },
    updateStartDate(date) {
      this.startDate = date;
      this.updateFilter();
    },

    updateEndDate(date) {
      this.endDate = date;
      this.updateFilter();
    }
  }
};
</script>
