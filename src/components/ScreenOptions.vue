<template>
  <div class="screen-options">
    <div class="screen-options__line" />
    <div class="screen-options__choices">
      <div class="screen-options__choices__title">
        <span> ¿Qué animal se esconde? </span>
      </div>
      <ul v-if="optionsToChoose.length" class="screen-options__choices__ul">
        <li><span v-text="toUpperCase(optionsToChoose[0].name)" /></li>
        <li><span v-text="toUpperCase(optionsToChoose[1].name)" /></li>
        <li><span v-text="toUpperCase(optionsToChoose[2].name)" /></li>
        <li><span v-text="toUpperCase(optionsToChoose[3].name)" /></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "ScreenOptions",
  props: {
    optionsToChoose: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    toUpperCase(text) {
      return text.toUpperCase();
    },
  },
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
.screen-options__choices {
  margin-left: 5px;
}
.screen-options__choices__title {
  margin: 10px 0;
}
.screen-options__choices__ul {
  display: flex;
  flex-wrap: wrap;
  list-style: none;
  padding-left: 5px;
}
.screen-options__choices__ul li {
  flex-basis: 50%;
  padding-left: 1rem;
  margin-bottom: 10px;
}

@media (min-width: 992px) {
  .screen-options {
    min-height: 250px;
  }
}
</style>
