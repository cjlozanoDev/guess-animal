<template>
  <div class="card-animal">
    <div class="card-animal__container-image">
      <img
        src="https://github.com/devcjlozano/apiGuessAnimal/blob/master/sprites/1.png?raw=true"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "CardAnimal",
};
</script>

<style scoped>
img {
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
</style>
