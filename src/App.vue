<template>
  <div>
    <h1>
      Hello World {{ counter }}
    </h1>
    <button @click="increaseCounter">Increase</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      counter: 0
    }
  },
  methods: {
    increaseCounter() {
      this.counter++
    }
  }
}
</script>

<style scoped>

</style>