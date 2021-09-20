<template>
  <div class="animal-record">
    <ul>
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
  height: 200px;
  background: url("../assets/images/notebook.png");
  background-repeat: repeat;
  border: 4px solid var(--secundary);
  padding: 10px;
}

@media (min-width: 768px) {
  .animal-record {
    height: 400px;
  }
}
</style>
