<template>
  <div class="card-animal">
    <div class="card-animal__container-image">
      <img :class="classImage" :src="urlAnimal" />
    </div>
  </div>
</template>

<script>
export default {
  name: "CardAnimal",
  props: {
    idAnimal: {
      type: Number,
      default: 0,
    },
    chosenOption: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    urlAnimal() {
      if (this.idAnimal === 0) {
        return "";
      }
      return `${process.env.VUE_APP_URL_ANIMAL_API}/${
        this.idAnimal
      }.png?raw=true?${Date.now()}`;
    },
    classImage() {
      return {
        "animal-image-hidden": !this.chosenOption,
      };
    },
  },
};
</script>

<style scoped>
img {
  width: 100%;
  margin-left: auto;
  margin-right: auto;
}
.card-animal {
  height: auto;
  min-width: 44%;
  max-width: 44%;
  background: url("../assets/images/notebook.png");
  background-repeat: repeat;
  border: 4px solid var(--secundary);
}
.card-animal__container-image {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 12px;
  height: 100%;
}
.animal-image-hidden {
  filter: brightness(0);
}

@media (min-width: 768px) {
  .card-animal {
    min-width: 40%;
    max-width: 40%;
  }
}

/* img {
  width: 100%;
  margin-left: auto;
  margin-right: auto;
}
.card-animal {
  width: 200px;
  height: 200px;
  background: url("../assets/images/notebook.png");
  background-repeat: repeat;
  border: 4px solid var(--secundary);
}
.card-animal__container-image {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 12px;
  height: 100%;
}

@media (min-width: 768px) {
  .card-animal {
    width: 400px;
    height: 400px;
  }
}

@media (min-width: 992px) {
  .card-animal {
    width: 600px;
    height: 600px;
  }
} */
</style>
