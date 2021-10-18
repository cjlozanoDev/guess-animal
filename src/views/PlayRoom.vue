<template>
  <div class="playroom">
    <div class="playroom__central-panel">
      <div class="playroom__central-panel__header">
        <div>GUESS ANIMAL</div>
        <div>Nombre: {{ playerName }}</div>
      </div>
      <div class="playroom__central-panel__main">
        <div class="playroom__central-panel__main__header">
          <CardAnimal :id-animal="foundAnimal.id" />
          <AnimalRecord />
        </div>
      </div>
      <div class="playroom__screen-options">
        <ScreenOptions
          :options-to-choose="optionsToChoose"
          @animal-choose="animalChoose"
        />
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
      foundAnimal: {
        id: 0,
      },
      foundsAnimalsArchive: [],
      optionsToChoose: [],
      chosenOption: false,
    };
  },
  created() {
    if (this.playerName === "") {
      this.$router.push({ name: "welcome" });
    } else {
      this.foundAnimalPrincipal();
      this.foundOptionsAnimals();
    }
  },
  methods: {
    foundAnimalPrincipal() {
      let randomNumberAnimal = this.getRandomNumber(43);
      let idAnimalRandom = animalsList[randomNumberAnimal].id;

      while (this.foundsAnimalsArchive.indexOf(idAnimalRandom) >= 0) {
        randomNumberAnimal = this.getRandomNumber(43);
        idAnimalRandom = animalsList[randomNumberAnimal].id;
      }
      this.foundAnimal = animalsList[randomNumberAnimal];
      this.foundsAnimalsArchive.push(this.foundAnimal.id);
    },
    foundOptionsAnimals() {
      let optionsToChooseAux = [
        {
          id: this.foundAnimal.id,
          name: this.foundAnimal.name,
        },
      ];
      let foundsAnimalsArchiveAux = [];
      let randomNumberAnimal = -1;

      while (optionsToChooseAux.length < 4) {
        randomNumberAnimal = this.getRandomNumber(43);
        let idAnimalRandom = animalsList[randomNumberAnimal].id;
        let animalFound = {};

        while (
          idAnimalRandom === this.foundAnimal.id ||
          foundsAnimalsArchiveAux.indexOf(idAnimalRandom) >= 0
        ) {
          randomNumberAnimal = this.getRandomNumber(43);
          idAnimalRandom = animalsList[randomNumberAnimal].id;
        }
        animalFound = animalsList[randomNumberAnimal];
        foundsAnimalsArchiveAux.push(idAnimalRandom);
        optionsToChooseAux.push({
          id: animalFound.id,
          name: animalFound.name,
        });
      }
      this.optionsToChoose = optionsToChooseAux.sort(() => Math.random() - 0.5);
    },
    getRandomNumber(max) {
      return Math.floor(Math.random() * max) + 1;
    },
    animalChoose(idAnimal) {
      this.chosenOption = true;

      if (idAnimal === this.foundAnimal.id) {
        alert(`Enhorabuena, era un/una ${this.foundAnimal.name}`);
      } else {
        alert("OOh!; ese no era el animal escondido");
      }
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
