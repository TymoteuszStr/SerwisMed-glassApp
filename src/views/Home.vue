<template>
  <div class="wrapper">
    <Glass />
    <Circle :size="300" style="bottom: 50px; left: 5%" />
    <Circle :size="340" style="top: 50px; right: 5%" />
  </div>
</template>

<script>
import Glass from "@/components/Glass.vue";
import Circle from "@/components/Circle.vue";
export default {
  name: "Home",
  components: {
    Glass,
    Circle,
  },
};
</script>
<style lang="scss">
.wrapper {
  min-height: 100vh;
  background: linear-gradient(to right top, #2596be, #6cdbeb);
  display: flex;
  align-items: center;
  max-width: 100vw;
}
</style>
