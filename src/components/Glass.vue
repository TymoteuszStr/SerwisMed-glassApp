<template>
   <div class="glass"></div>
</template>

<script>
export default {
name: 'Glass',

}
</script>
<style lang="scss" scoped="true">
  .glass{
    min-height: 80vh;
    width: 70%;
    background: linear-gradient(to right bottom , rgba(255,255,255,0.7),rgba(255,255,255,0.3));
    margin-left: auto;
    margin-right: auto;
    border-radius: 20px;
    z-index: 10;
    backdrop-filter: blur(24px);
  }
</style>