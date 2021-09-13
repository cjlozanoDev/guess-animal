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
        <div>
          <input
            class="input-text"
            type="text"
            placeholder="Escribe tu nombre"
          />
          <button class="button__start">EMPEZAR A JUGAR</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
};
</script>

<style scoped>
.home {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.home__principal__box {
  text-align: center;
  background-color: #fff;
  padding: 20px;
  width: 95%;
}
.home__principal__box__title {
  font-size: 2em;
}
.input-text {
  height: 40px;
}
.button__start {
  height: 40px;
  background-color: var(--primary);
}

@media (min-width: 768px) {
  .home__principal__box {
    width: 80%;
  }
}
</style>
