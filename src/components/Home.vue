<template>
  <div>
    <div v-if="states">
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
      arrState: [],
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
