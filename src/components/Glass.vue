<template>
  <div class="glass">
    <Dashboard class="dashboard" @navNr="setCurrentPage" />
    <Description v-if="showText" :textNr="currentPage" />
  </div>
</template>

<script>
import Dashboard from "@/components/Dashboard.vue";
import { ref } from "vue";
import Description from "@/components/Description.vue";
export default {
  name: "Glass",
  components: {
    Dashboard,
    Description,
  },
  setup() {
    let currentPage = ref(0);
    const setCurrentPage = ($event) => {
      currentPage.value = $event;
    };
    const showText = window.innerWidth >= 1280 ? true : false;

    return { setCurrentPage, currentPage, showText };
  },
};
</script>
<style lang="scss" scoped="true">
.glass {
  display: flex;
  min-height: 80vh;
  width: 70%;
  background: linear-gradient(
    to right bottom,
    rgba(255, 255, 255, 0.7),
    rgba(255, 255, 255, 0.3)
  );
  margin-left: auto;
  margin-right: auto;
  border-radius: 20px;
  z-index: 10;
  backdrop-filter: blur(24px);
}

@media (max-width: 1024px) {
  .glass {
    width: 80%;

    .dashboard {
      width: 100%;
    }
  }
}
</style>
