<template>
  <div class="glass" id="glass">
    <Dashboard class="dashboard" @navNr="setCurrentPage" />
    <Description v-if="showText" :textNr="currentPage" />
  </div>
</template>

<script>
import Dashboard from "@/components/Dashboard.vue";
import { onMounted, ref } from "vue";
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
    let showText = ref(window.innerWidth >= 960 ? true : false);

    const toggleMobileView = () => {
      showText.value = window.innerWidth >= 960 ? true : false;
    };

    window.addEventListener("resize", toggleMobileView);

    onMounted(() => {
      const glassCard = document.querySelector("#glass");
      glassCard.addEventListener("mousemove", (e) => {
        let xAxis = (window.innerWidth / 2 - e.pageX) / 100;
        let yAxis = (window.innerHeight / 2 - e.pageY) / 100;
        glassCard.style.transform = `rotateY(${xAxis}deg) rotateX(${yAxis}deg)`;
      });
    });
    return { setCurrentPage, currentPage, showText };
  },
};
</script>
<style lang="scss" scoped="true">
.glass {
  transform-style: preserve-3d;
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
  max-height: 80vh;
  box-shadow: 0px 20px 20px rgba(0, 0, 0, 0.2), 0px 0px 50px rgba(0, 0, 0, 0.2);
}

@media (max-width: 959px) {
  .glass {
    width: 80%;
    max-height: initial;
    min-height: 70vh;
    .dashboard {
      width: 100%;
      max-height: initial;
    }
  }
}
</style>
