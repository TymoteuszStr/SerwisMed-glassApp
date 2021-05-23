<template>
  <div class="who">
    <div class="who__picture"></div>
    <h2 class="who__name">Maria Stróżniak</h2>
    <span class="who__subName">mgr pielęgnierstwa</span>
  </div>
</template>

<script>
export default { name: "Who" };
</script>

<style lang="scss" scoped>
.who {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;

  &__picture {
    background-image: url("../assets/maria2.jpg");
    width: 180px;
    height: 180px;
    border-radius: 50%;
    background-position: center;
    background-size: cover;
    margin-top: 30px;
  }

  &__name {
    margin-top: 30px;
    color: rgb(5, 102, 141);
    font-size: 26px;
    font-family: "Karla", sans-serif;
    font-weight: 600;
  }

  &__subName {
    color: rgb(5, 102, 141);
    font-size: 20px;
    font-family: "Karla", sans-serif;
    font-weight: 400;
  }
}
</style>
