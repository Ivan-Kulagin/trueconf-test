<template>
  <div class="cabin"></div>
</template>

<script>
export default {
  name: "ElevatorCabin",
  watch() {

  }
}
</script>

<style scoped lang="scss">
@import 'src/styles/base';

.cabin {
  width: $base-width;
  height: $base-height;
  background-color: darkred;
  transition: transform 1s;
  transform: translate(0, 0*($base-width+$row-gap));
}
</style>