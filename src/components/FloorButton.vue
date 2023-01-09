<template>
  <button @click="handleButtonClick">
    Go to {{ floor }}
  </button>
</template>

<script>
export default {
  name: "FloorButton",
  props: {
    floor: {
      type: Number,
      required: true
    }
  },

  methods: {
    handleButtonClick() {
      this.$emit('set-cabin', this.floor)
    }
  }
}
</script>

<style scoped>

</style>