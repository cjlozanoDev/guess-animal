<template>
  <div class="playroom">
    <div class="playroom__central-panel">
      <div class="playroom__central-panel__header">
        <div>GUESS ANIMAL</div>
        <div>Nombre: {{ playerName }}</div>
      </div>
      <div class="playroom__central-panel__main">
        <div class="playroom__central-panel__main__header">
          <CardAnimal />
          <AnimalRecord />
        </div>
      </div>
      <div class="playroom__screen-options">
        <ScreenOptions />
      </div>
    </div>
  </div>
</template>

<script>
import CardAnimal from "../components/CardAnimal.vue";
import AnimalRecord from "../components/AnimalRecord.vue";
import ScreenOptions from "../components/ScreenOptions.vue";
import animalsList from "../api/index.js";

export default {
  name: "PlayRoom",
  components: {
    CardAnimal,
    AnimalRecord,
    ScreenOptions,
  },
  props: {
    playerName: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      foundAnimal: {},
      foundsAnimalsArchive: [],
    };
  },
  created() {
    if (this.playerName === "") {
      this.$router.push({ name: "welcome" });
    } else {
      this.foundAnimalPrincipal();
      // this.foundOptionsAnimals();
    }
  },
  methods: {
    foundAnimalPrincipal() {
      let randomNumberAnimal = this.getRandomNumber(43);
      while (animalsList.indexOf === -1) {
        randomNumberAnimal = this.getRandomNumber(43);
      }
      this.foundAnimal = animalsList[randomNumberAnimal];
      this.foundsAnimalsArchive.push(this.foundAnimal.id);
    },
    getRandomNumber(max) {
      return Math.floor(Math.random() * max) + 1;
    },
  },
};
</script>

<style scoped>
.playroom {
  display: flex;
  justify-content: center;
}
.playroom__central-panel {
  background: var(--secundary-ligh);
  width: 95%;
  min-height: 100vh;
}
.playroom__central-panel__header {
  background: var(--secundary);
  color: var(--secundary-ligh);
  padding: 10px;
  display: flex;
  justify-content: space-between;
}
.playroom__central-panel__header,
.playroom__central-panel__main,
.playroom__screen-options {
  padding: 10px;
}
.playroom__central-panel__main__header {
  display: flex;
  gap: 2px;
}

@media (min-width: 768px) {
  .playroom__central-panel {
    width: 90%;
  }
}
</style>
