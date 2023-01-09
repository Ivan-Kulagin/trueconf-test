<template>
  <div
    class="cabin"
    :style="{...cellStyle, ...{marginBottom: currentMarginBottom}}"
  />
</template>

<script>
export default {
  name: "CabinCell",
  props: {
    // active: {
    //   type: Boolean,
    //   default: true,
    // },
    floor: {
      type: Number,
      required: true,
    },
    move: {
      type: Number,
      required: true,
    }
  },

  data() {
    return {
      currentMarginBottom: ''
    }
  },

  watch: {
    floor(newVal) {
      if (!newVal) return
      setTimeout(() => {
        this.$emit('set-move', 0)
        this.currentMarginBottom = `${(this.floor-1)*105}px`
      }, Math.abs(this.move) * 1000)
    }
  },

  computed: {
    cellStyle() {
      return {
        transition: `transform ${Math.abs(this.move)}s`,
        transform: `translate(0, ${this.move * 105}px)`,
        backgroundColor: 'darkred',
      }
    },
  }
}
</script>

<style scoped lang="scss">
@import 'src/styles/base';

.cabin {
  display: flex;
  width: $base-width;
  height: $base-height;
}

.active {
  transition: transform 1s;
  transform: translate(0, 2*($base-width+$row-gap));
}
</style>