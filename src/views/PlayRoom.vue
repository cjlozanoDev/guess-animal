<template>
  <div class="playroom">
    <div class="playroom__central-panel">
      <div class="playroom__central-panel__header">
        <div>GUESS ANIMAL</div>
        <div>Nombre: {{ playerName }}</div>
      </div>
      <div class="playroom__central-panel__main">
        <div>Hola</div>
        <div>Adios</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PlayRoom",
  props: {
    playerName: {
      type: String,
      default: "",
    },
  },
  created() {
    if (this.playerName === "") {
      this.$router.push({ name: "welcome" });
    }
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
.playroom__central-panel__main {
  padding: 10px;
}

@media (min-width: 768px) {
  .playroom__central-panel {
    width: 90%;
  }
}
</style>
