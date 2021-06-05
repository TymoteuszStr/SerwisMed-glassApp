<template>
  <div class="dashboard">
    <Who />
    <Nav class="nav" @navNr="emitNavNr" />
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
@import "@/common/variables.scss";
.dashboard {
  @include noselect;
  min-height: inherit;
  min-width: 380px;
  position: relative;
  top: 0;
  left: 0;
  background-color: rgba(255, 255, 255, 0.3);
  border-radius: inherit;
}

@media (max-width: 959px) {
  .dashboard {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: inherit;
    min-width: initial;
    background-color: rgba(255, 255, 255, 0);
    height: auto;
    .nav {
      width: inherit;
    }
  }
}
@media (max-width: 1280px) {
  .dashboard {
    min-width: 280px;
  }
}
</style>
