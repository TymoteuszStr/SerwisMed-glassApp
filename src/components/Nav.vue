<template>
  <ul class="navList">
    <li
      v-for="(item, index) in navList"
      :key="index"
      class="navItem"
      @click="navClickHandle(index)"
      :class="{ activeItem: currentPage === index }"
    >
      {{ item }}
      <transition name="show">
        <Description v-if="currentPage === index && showText" :textNr="currentPage" />
      </transition>
    </li>
  </ul>
</template>

<script>
import { ref } from "vue";
import Description from "@/components/Description.vue";

export default {
  name: "Nav",
  components: { Description },
  setup(props, { emit }) {
    const navList = ["O mnie", "Usługi", "Kontakt"];
    let currentPage = ref(null);
    const showText = ref(window.innerWidth < 960 ? true : false);

    const hideDescription = () => {
      currentPage.value = null;
    };
    const emitNavNr = (index) => {
      currentPage.value = index;
      emit("navNr", currentPage.value);
    };

    const navClickHandle = (index) => {
      if (currentPage.value === index) hideDescription();
      else emitNavNr(index);
    };

    const toggleMobileView = () => {
      showText.value = window.innerWidth < 960 ? true : false;
    };

    window.addEventListener("resize", toggleMobileView);
    return { navList, currentPage, showText, navClickHandle };
  },
};
</script>

<style lang="scss" scoped>
@import "@/common/variables.scss";

.navList {
  @include noselect;
  list-style: none;
  max-width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-top: 50px;
  .navItem {
    color: rgb(5, 102, 141);
    padding: 10px 0;
    font-size: 20px;
    letter-spacing: 1px;

    &:hover {
      color: rgb(84, 207, 255);
      cursor: pointer;
    }
  }
  .activeItem {
    color: rgb(84, 207, 255);
  }
}

@media (max-width: 959px) {
  .navList {
    .navItem {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 100%;
    }
  }
}

//animation
.show-enter-active,
.show-leave-active {
  transition: all 0.4s ease-out;
}
.show-enter-from,
.show-leave-to {
  opacity: 0;
  height: 0;
}
</style>
