<template>
  <div class="textWrapper">
    <p class="text" v-for="(item, index) in text" :key="index">
      <img class="syringe" src="@/assets/syringe.svg" />
      {{ item }}
    </p>
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
  justify-content: center;
  margin-left: auto;
  margin-right: auto;
  padding: 50px;
  overflow-y: auto;
  align-items: flex-start;
  .text {
    display: flex;
    align-items: flex-start;
    position: relative;
    top: 0;
    left: 0;
    padding: 10px 0;
    font-size: 22px;
    font-weight: 600;
    color: #05668d;
    .syringe {
      width: 20px;
      height: 20px;
      margin-right: 10px;
      margin-top: 5px;
    }
  }
}
@media (max-width: 959px) {
  .textWrapper {
    background: linear-gradient(
      to right bottom,
      rgba(255, 255, 255, 0.7),
      rgba(255, 255, 255, 0.3)
    );
    top: auto;
    left: 0;
    height: 400px;
    width: inherit;
    text-align: flex-start;
    overflow-y: scroll;
    padding: 0;
    border-end-end-radius: 10px;
    border-end-start-radius: 10px;

    .text {
      margin: 0;
      padding: 0px 20px;
      font-size: 16px;
      font-weight: 400;
      min-width: 320px;
      max-width: 330px;
      margin-left: auto;
      margin-right: auto;
      text-align: start;
      &:last-child {
        letter-spacing: 0px;
      }
    }
  }
}
</style>
