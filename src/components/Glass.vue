<template>
   <div class="glass">
       <Dashboard />
   </div>
</template>

<script>
import Dashboard from '@/components/Dashboard.vue'
export default {
name: 'Glass',
components:{
    Dashboard,
}
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
  
  @media (max-width:1280px)
  {
    .glass{
    width: 80vw;
    }
  }
</style>