<template>
 <div class="wrapper">
   <div class="glass"></div>
 </div>

</template>

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

  .glass{
    min-height: 90vh;
    width: 80%;
    background: linear-gradient(to right bottom , rgba(255,255,255,0.7),rgba(255,255,255,0.3));
    margin-left: auto;
    margin-right: auto;
    border-radius: 15px;
  }
  
}

</style>
