<template>
  <div id="app">
    <div>
      <CriteriaFilter :dynamicText="parentDynamicText" @filterChanged="onFilterChanged" />
      <input v-text="parentDynamicText" v-model="parentDynamicText" />
    </div>
  </div>
</template>

<script>
import CriteriaFilter from "./components/CriteriaFilter.vue";
export default {
  name: "Reports",
  components: {
    CriteriaFilter
  },
  data() {
    return {
      parentDynamicText: "",
      startDateSelected: new Date(),
      endDateSelected: new Date()
    };
  },
  methods: {
    // onStartDateChanged(filterData) {
    //   console.log(filterData);
    // },
    onFilterChanged(criteria) {
      console.log("Filter changed to: ");
      console.log(criteria);
    }
  }
};
</script>