<template>
  <div class="wrapper">
    <Glass />
    <Circle :size="300" style="bottom: 50px; left: 150px" />
    <Circle :size="340" style="top: 50px; right: 150px" />
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
}
</style>
