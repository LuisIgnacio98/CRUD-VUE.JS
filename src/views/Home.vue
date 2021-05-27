<template>
  <h1 class="my-5">CRUD con Vue.js <img :src="logo" /> </h1>
  <form @submit.prevent="procesarFormulario">
    <Input :tarea="tarea" />
  </form>
  <hr />
  <ListaTarea />
</template>

<script>
import Input from "../components/Input";
import ListaTarea from "../components/ListaTarea";
import Logo from '../assets/logo.svg'

import { mapActions } from "vuex";
const shortid = require("shortid");

export default {
  name: "Home",
  data() {
    return {
      logo: Logo,
      tarea: {
        id: "",
        nombre: "",
        categorias: [],
        estado: "",
        numero: 0,
      },
    };
  },
  methods: {
    ...mapActions(["setTareas"]),
    procesarFormulario() {
      if (this.tarea.nombre.trim() === "") {
        console.log("Campo vacio");
        return;
      }
      //Generar Id
      this.tarea.id = shortid.generate();
      //Enviar datos
      this.setTareas(this.tarea);
      //Limpiar Datos
      this.tarea = {
        id: "",
        nombre: "",
        categorias: [],
        estado: "",
        numero: 0,
      };
    },
  },

  components: {
    Input,
    ListaTarea,
    Logo
  },
};
</script>

<style scoped>
img{
  width: 30px;
  height: 30px;
}
</style>
