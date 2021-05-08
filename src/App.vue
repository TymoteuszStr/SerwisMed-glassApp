<template>
 <div class="wrapper">
 <Glass />
 <Circle :size="300" style="bottom:50px; left:150px;"/>
 <Circle :size="340" style="top:50px; right:150px;"/>
 </div>

</template>

<script>
import Glass from '@/components/Glass.vue'
import Circle from '@/components/Circle.vue'
export default {
name: 'App',
components:{
  Glass,Circle
}
}
</script>
<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Karla:wght@400;600&display=swap');

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
