<template>
  <div class="animal-record">
    <ul class="animal-record__ul">
      <li>Nombre: Ciervo</li>
      <li>Especie: Cérvido</li>
      <li>Clase de animal: Mamífero vertebrado</li>
      <li>Tipo de comida: Hervívoro</li>
      <li>Forma de reproducción: Vivíparo</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "AnimalRecord",
};
</script>

<style scoped>
.animal-record {
  width: 100%;
  font-size: 0.9em;
  background: url("../assets/images/notebook.png");
  background-repeat: repeat;
  border: 4px solid var(--secundary);
  padding: 10px;
}

.animal-record__ul {
  margin: 0;
  padding-left: 24px;
  line-height: 1.5em;
}

@media (min-width: 768px) {
  .animal-record__ul {
    line-height: 2.5em;
  }
}
@media (min-width: 992px) {
  .animal-record {
    font-size: 1em;
  }
  .animal-record__ul {
    line-height: 3.5em;
  }
}
@media (min-width: 1140px) {
  .animal-record {
    font-size: 1.2em;
  }
}
</style>
