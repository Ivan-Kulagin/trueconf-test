<template>
  <Schema
    :floors="floors"
    :shafts="shafts"
  />
</template>

<script>
import Schema from "./components/Schema";

export default {
  name: "App",
  components: {
    Schema
  },

  data() {
    return {
      floors: 5,
      shafts: 1
    }
  },
}
</script>

<style scoped>

</style>