<template>
  <div class="animal-record">
    <ul class="animal-record__ul">
      <li>Nombre: Ciervo</li>
      <li>Especie: Alguna</li>
      <li>Tipo Comida: Hervívoro</li>
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
}

@media (min-width: 992px) {
  .animal-record {
    font-size: 1em;
  }
}
@media (min-width: 1140px) {
  .animal-record {
    font-size: 1.2em;
  }
}
</style>
