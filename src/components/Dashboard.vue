<template>
<div class="dashboard">
    <div class="who">
        <div class="who__picture"></div>
        <h2 class="who__name">Maria Stróżniak</h2>
        <span class="who__subName">mgr pielęgnierstwa</span>
    </div>
    <ul class="navList">
      <li class="navItem">O mnie</li>
      <li class="navItem">Usługi</li>
      <li class="navItem">Cennik</li>
      <li class="navItem">Pomoc</li>
    </ul>
</div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.dashboard {
    min-height: inherit;
    width: 30% !important;
    position: relative;
    top: 0;
    left: 0;
    background-color: rgba(255, 255, 255, 0.3);
    border-radius: inherit;

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
            /* Center the image */
            background-size: cover;
            /* Resize the background image to cover the entire container */
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
}
</style>
