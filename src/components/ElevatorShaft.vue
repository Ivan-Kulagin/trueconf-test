<template>
  <div class="shaft" :style="{height: this.computedHeight + 'px'}">
    <CabinCell class="cell" :move="move" :floor="cabin" @set-move="setMove" />
  </div>
</template>

<script>
import CabinCell from "./CabinCell";

export default {
  name: "ElevatorShaft",
  components: {CabinCell},
  props: {
    floors: {
      type: Number,
      required: true
    },
    cabin: {
      type: Number,
      required: true
    }
  },

  data() {
    return {
      move: 0,
    }
  },

  watch: {
    cabin(from, to) {
      if (!from || !to) return
      this.move = to - from
      console.log('move', this.move)
    }
  },

  computed: {
    computedHeight() {
      return this.floors * 105
    }
  },

  methods: {
    setMove(value) {
      this.move = value
    }
  }
}
</script>

<style scoped lang="scss">
@import 'src/styles/base';

.shaft {
  background-color: lightslategrey;
  display: flex;
//  display: flex;
//  flex-direction: column-reverse;
//  gap: $row-gap;
}

.cell {
  align-self: flex-end;
}
</style>