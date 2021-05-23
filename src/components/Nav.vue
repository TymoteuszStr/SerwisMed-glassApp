<template>
  <ul class="navList">
      <li v-for="(item,index) in navList" :key="index" class="navItem">{{item}}</li>
    </ul>
</template>

<script>
export default {
    name:'Nav',
    setup(){
        const navList=['O mnie', 'Usługi', 'Cennik'];

        return {navList}

    }

}
</script>

<style lang="scss" scoped>

    .navList{
      list-style: none;
      width:100%;
      display:flex;
      flex-direction: column;
      justify-content:center;
      align-items: center;
      margin-top: 50px;
      .navItem{
            color: rgb(5, 102, 141);
            padding: 10px 0;
            font-size: 20px;
            letter-spacing: 1px;

            &:hover{
              color: white;
              cursor: pointer;
            }
      }
    }
</style>