<template>
  <div class="container mt-5">
    <div class="row align-items-center">
      <div class="col-12 col-md-6" v-if="states">
        <h1 class="mb-3">{{ title }}</h1>
        <h3 class="mb-4">{{ subtitle }}</h3>
        <v-select
            multiple
            :debounce="250"
            :options="stateArr"
            label="displayValue"
            :value.sync="newFilters"
            :taggable="true"
            placeholder="Filter states"
          ></v-select>
      </div>
      <div v-else>
        <h1>Loading</h1>
      </div>
      <div class="img-container col-12 col-md-6 mt-5">
        <img src="@/assets/slider.png">
      </div>
    </div>
  </div>
</template>

<script>
import vSelect from 'vue-select'

export default {
  components: {
    vSelect
  },
  props: ['states'],
  name: 'Home',
  data () {
    return {
      title: 'Smart data, powerful decisions',
      subtitle: 'Instant access to all kinds of data sources',
      newFilters: []
    }
  },
  computed: {
    stateArr: function () {
      return Object.values(this.states)
    }
  }
}
</script>

<style scoped>
h1 {
  font-weight: bolder;
  font-size: 3rem;
  color: #ffffff;
}
h3 {
  font-size: 1.5rem;
  color: #afbdd0;
}
img {
  width: 100%;
}
.v-select {
  background-color: #ffffff;
  border: none;
}
.v-select.dropdown.open .dropdown-toggle,
.v-select.dropdown.open .dropdown-menu {
  border-color: #4CC3D9;
  padding: 0;
  border: none;
}
@media (max-width: 768px) {
  h1 {
    font-size: 2.25rem;
  }
}
@media (min-width: 992px) {
  .row {
    flex-direction: row-reverse;
  }
}
</style>
