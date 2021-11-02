<template>
  <div>
    <button @click="onclick" :class="classObject">
      <slot />
    </button>
  </div>
</template>

<script>
export default {
  name: "Button",
  props: {
    type: {
      type: String,
      default: "primary",
    },
    onclick: {
      type: Function,
      default: () => {},
    },
  },
  data() {
    return {
      classObject: {
        "button-guess-animal": true,
        primary: this.type === "primary",
        next: this.type === "next",
      },
    };
  },
};
</script>

<style scoped>
.primary {
  background-color: var(--primary);
  border: 2px solid var(--secundary);
}
.next {
  color: #fff;
  border: 4px solid var(--secundary-ligh);
  background-color: var(--secundary);
}
</style>
