<template>
  <div class="wrapper">
    <div class="shafts">
      <ElevatorShaft v-for="shaft in shafts" :floors="floors" :cabin="cabin" :key="shaft" />
    </div>
    <div class="buttons">
      <FloorButton class="button" v-for="floor in floors" :floor="floor" :key="floor" @set-cabin="setCabin" />
    </div>
  </div>
</template>

<script>
import ElevatorShaft from "./ElevatorShaft";
import FloorButton from "./FloorButton";

export default {
  name: "Schema",
  components: {
    ElevatorShaft,
    FloorButton
  },

  props: {
    floors: {
      type: Number,
      required: true
    },
    shafts: {
      type: Number,
      required: true
    }
  },

  data() {
    return {
      cabin: 1,
    }
  },

  methods: {
    setCabin(floor) {
      this.cabin = floor
      console.log('setCabin (go to)', this.cabin)
    }
  }
}
</script>

<style scoped lang="scss">
@import 'src/styles/base';

.wrapper {
  display: flex;
  flex-direction: row;
  gap: $column-gap;
}

//.shafts {
//  display: flex;
//  flex-direction: row;
//  gap: $column-gap;
//}

.buttons {
  display: flex;
  flex-direction: column-reverse;
  gap: $row-gap;
}

.button {
  width: $base-width;
  height: $base-height;
}
</style>