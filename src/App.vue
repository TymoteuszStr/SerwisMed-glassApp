<template>
  <Home />
</template>

<script>
import Home from "@/views/Home.vue";
export default {
  name: "App",
  components: {
    Home,
  },
};
</script>
<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Karla:wght@400;600&display=swap");

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
