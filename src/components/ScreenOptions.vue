<template>
  <div class="screen-options">
    <div class="screen-options__line" />
  </div>
</template>

<script>
export default {
  name: "ScreenOptions",
};
</script>

<style scoped>
.screen-options {
  position: relative;
  background: var(--yellow-jungle);
  min-height: 200px;
  border: 4px solid var(--secundary);
  padding: 10px;
}
.screen-options::after {
  position: absolute;
  top: -10px;
  content: "¿Sabes qué animal es?";
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
  height: 20px;
  width: calc(100% - 20px);
  background: var(--secundary);
}

@media (min-width: 992px) {
  .screen-options {
    min-height: 250px;
  }
}
</style>
