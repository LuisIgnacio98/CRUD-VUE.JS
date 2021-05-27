<template>
  <input
    type="text"
    class="form-control my-2"
    placeholder="Ingrese nombre"
    v-model.trim="tarea.nombre"
  />
  <div class="form-check form-check-inline">
    <input
      type="checkbox"
      class="form-check-input"
      id="check-1"
      v-model="tarea.categorias"
      value="Javascript"
    />
    <label class="form-check-label" for="check-1">Javascript</label>
  </div>
  <div class="form-check form-check-inline">
    <input
      type="checkbox"
      class="form-check-input"
      id="check-2"
      v-model="tarea.categorias"
      value="Node.js"
    />
    <label class="form-check-label" for="check-2">Node.js</label>
  </div>

  <div class="mt-2">
    <div class="form-check form-check-inline">
      <input
        type="radio"
        class="form-check-input"
        id="radio-1"
        v-model="tarea.estado"
        value="Urgente"
      />
      <label class="form-check-label" for="radio-1">Urgente</label>
    </div>
    <div class="form-check form-check-inline">
      <input
        type="radio"
        class="form-check-input"
        id="radio-2"
        v-model="tarea.estado"
        value="Relax"
      />
      <label class="form-check-label" for="radio-1">Relax</label>
    </div>
  </div>
  <div class="mt-2">
    <input class="form-control" type="number" v-model.number="tarea.numero" />
  </div>
  <button
    class="btn btn-dark mt-2 btn-block"
    type="submit"
    :disabled="bloquear"
  >
    Procesar
  </button>
</template>

<script>
export default {
  props: {
    tarea: Object,
  },
  computed: {
    bloquear() {
      return this.tarea.nombre.trim() === "" ? true : false;
    },
  },
};
</script>

<style></style>
