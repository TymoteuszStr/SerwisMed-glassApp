<template>
 <div class="wrapper">
 <Glass />
 </div>

</template>

<script>
import Glass from '@/components/Glass.vue'
export default {
name: 'App',
components:{
  Glass
}
}
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.wrapper{
  min-height: 100vh;
  background: linear-gradient(to right top, #2596be, #6cdbeb);
  display: flex;
  align-items: center;

}

</style>
