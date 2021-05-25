<template>
  <div class="textWrapper">
    <p class="text" v-for="(item, index) in text" :key="index">{{ item }}</p>
  </div>
</template>

<script>
import { onUpdated, ref, toRefs } from "vue";
export default {
  name: "Description",
  props: {
    textNr: {
      type: Number,
      required: true,
    },
  },
  setup(props) {
    const { textNr } = toRefs(props);

    let showText = ref(window.innerWidth <= 1280 ? true : false);
    const oMnie = [
      "Prowadzę jednoosobową praktykę pielęgniarską",
      "Jestem magistrem pielęgniarstwa ze specjalizacja w opiece paliatywnej.",
      "Świadczę usługi zgodnie z zakresem i możliwościami jakie daje mi prawo wykonywania zawodu w zawodzie pielęgniarki.",
      "Dojadę do pacjenta w Jaworznie i jego okolicach",
    ];
    const uslugi = [
      "porada pielęgniarska",
      "iniekcje w domu pacjenta",
      "podłączenie kroplówki",
      "pobranie materiału do badań",
      "pomiar parametrów życiowych",
      "opieka pielęgniarska",
      "szkolenia w zakresie pielęgniarstwa",
    ];
    const kontakt = ["Maria Stróżniak", "tel.: 693106186", "maria.strozniak@gmail.com"];
    const assets = [oMnie, uslugi, kontakt];
    let text = ref(assets[textNr.value]);
    onUpdated(() => {
      text.value = assets[textNr.value];
    });
    return { text, textNr, showText };
  },
};
</script>

<style lang="scss" scoped>
.textWrapper {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  margin: 100px 150px;
  .text {
    position: relative;
    top: 0;
    left: 0;
    padding: 20px 0;
    font-size: 24px;
    font-weight: 600;
    color: rgb(7, 70, 95);
  }
}
@media (max-width: 1280px) {
  .textWrapper {
    background: linear-gradient(
      to right bottom,
      rgba(255, 255, 255, 0.7),
      rgba(255, 255, 255, 0.3)
    );
    top: auto;
    left: 0;
    width: 80vw;
    height: auto;
    margin: 0;
    padding:10px;

    .text {
      height: auto;
      margin: 0;
      padding: 10px 0;
      font-size: 18px;
      font-weight: 400;
      color: rgb(13, 91, 122);
    }
  }
}
</style>
