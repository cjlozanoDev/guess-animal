<template>
  <div class="home">
    <div class="home__principal__box">
      <div class="home__principal__box__title">
        <span>¡¡BIENVENIDO!!</span>
      </div>
      <div>
        <p>
          Estamos de excursión en la selva en busca de animales para poder
          fotografiarlos.
        </p>
        <p>
          Necesito tu ayuda para identificarlos y saber de que animal se trata
          para poder añadirlo a nuestro álbum fotográfico
        </p>
        <p>
          ¿Me quieres ayudar?, si es así, dime como te llamas para empezar a
          jugar.
        </p>
        <p>Escribe tu nombre aquí debajo</p>
        <div class="home__actions">
          <input
            class="input-guess-animal"
            type="text"
            v-model="playerName"
            placeholder="Escribe tu nombre"
          />
          <Button :onclick="startPlay" class="button-guess-animal">
            <span> EMPEZAR A JUGAR </span>
          </Button>
        </div>
        <div v-if="nameEmpty" class="home__error">
          <p>Para poder jugar, tienes que escribir tu nombre</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "../components/Button.vue";
// @ is an alias to /src

export default {
  name: "Welcome",
  components: {
    Button,
  },
  data() {
    return {
      playerName: "",
      tryPlay: false,
    };
  },
  computed: {
    nameEmpty() {
      return this.playerName === "" && this.tryPlay;
    },
  },
  methods: {
    startPlay() {
      if (this.playerName !== "") {
        this.$router.push({
          name: "PlayRoom",
          params: {
            playerName: this.playerName,
          },
        });
      }
      this.tryPlay = true;
    },
  },
};
</script>

<style scoped>
.home {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.home__actions {
  display: flex;
  justify-content: center;
  align-items: center;
}
.home__principal__box {
  text-align: center;
  background-color: #fff;
  border: 2px solid var(--secundary);
  padding: 20px;
  width: 95%;
}
.home__principal__box__title {
  font-size: 2em;
}
.home__error {
  color: var(--secundary);
  font-weight: bold;
}

@media (min-width: 768px) {
  .home__principal__box {
    width: 80%;
  }
}
</style>
