<template>
  <div class="dashboard">
    <Who />
    <Nav @navNr="emitNavNr" />
  </div>
</template>

<script>
import Nav from "./Nav.vue";
import Who from "./Who.vue";

export default {
  name: "Dashboard",
  components: {
    Who,
    Nav,
  },
  setup(props, { emit }) {
    const emitNavNr = ($event) => {
      emit("navNr", $event);
    };
    return { emitNavNr };
  },
};
</script>

<style lang="scss" scoped>
.dashboard {
  min-height: inherit;
  min-width: 380px;
  position: relative;
  top: 0;
  left: 0;
  background-color: rgba(255, 255, 255, 0.3);
  border-radius: inherit;
}

@media (max-width: 1280px) {
  .dashboard {
    max-width: 80vw;
    height: auto;
      min-width: 100px;
  }
}
</style>
