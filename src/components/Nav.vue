<template>
  <ul class="navList">
      <li
        v-for="(item, index) in navList"
        :key="index"
        class="navItem"
        @click="emitNavNr(index)"
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
    let currentPage = ref(0);
    const emitNavNr = (index) => {
      currentPage.value = index;
      emit("navNr", currentPage.value);
    };
   const showText = window.innerWidth <1280? true:false

    return { navList, emitNavNr, currentPage,showText };
  },
};
</script>

<style lang="scss" scoped>
.navList {
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

@media (max-width: 1280px) {
  .navList {
    .navItem {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
  }
}

//animation
.show-enter-active,
.show-leave-active {
  transition: all 0.3s ease-out;
}
.show-enter-from,
.show-leave-to {
  opacity: 0;
  height: 0;
}
</style>
