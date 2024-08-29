<script>
import Header from "./components/Header.vue";
import Hero from "./components/Hero.vue";
import Persona from "./components/Persona.vue";
import Instrumentos from "./components/Instrumentos.vue";
import ButtonView from "./components/ButtonView.vue";
import Card from "./components/Card.vue";

export default {
  components: {
    Header,
    Hero,
    Persona,
    Instrumentos,
    ButtonView,
    Card,
  },
  data() {
    return {
      personas: [
        {
          foto: "https://avatars.githubusercontent.com/u/499550?v=4",
          nombre: "Bruce Lee",
          descripcion: "Creador de Viu.Js",
        },
        {
          foto: "https://avatars.githubusercontent.com/u/499552?v=4",
          nombre: "Juan Perez",
          descripcion: "Creador de Linux",
        },
        {
          foto: "https://avatars.githubusercontent.com/u/499553?v=4",
          nombre: "Pedro Lopez",
          descripcion: "Creador de Java",
        },
      ],
      instrumentos: [
        {
          nombre: "Violin",
          icono: "mdi-violin",
        },
        {
          nombre: "Guitarra",
          icono: "mdi-guitar-pick",
        },
        {
          nombre: "Piano",
          icono: "mdi-piano",
        },
        {
          nombre: "Flauta",
          icono: "mdi-flute",
        },
        {
          nombre: "Trompeta",
          icono: "mdi-trumpet",
        },
        {
          nombre: "Tuba",
          icono: "mdi-tuba",
        },
        {
          nombre: "Bajo",
          icono: "mdi-bass",
        },
        {
          nombre: "Saxofon",
          icono: "mdi-saxophone",
        },
      ],
    };
  },
};
</script>
<template>
  <Header />
  <Hero />
  <section class="personas">
    <div v-for="(persona, i) in personas" :key="persona.nombre">
      <Persona
        :foto="persona.foto"
        :nombre="persona.nombre"
        :descripcion="persona.descripcion"
        @eliminarPersona="personas.splice(i, 1)"
      />
    </div>
    <div v-for="(instrumento, i) in instrumentos" :key="instrumento.nombre">
      <Instrumentos
        :instrumentos="[instrumento]"
        @eliminarInstrumento="instrumentos.splice(i, 1)"
      />
    </div>
  </section>
  <section>
    <ButtonView>
      <h3>Este es un Slot</h3>
    </ButtonView>
  </section>

  <section>
    <Card imagen="https://via.placeholder.com/300">
      <h1>Mi Título</h1>
      <p>Esta es una breve descripción de la tarjeta.</p>
      <button>Ver Más</button>
    </Card>
  </section>
</template>

<style scoped>
.personas {
  width: 80%;
  margin: 30px auto;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}
</style>
