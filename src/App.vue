<template>
  <Navbar />
  <div class="container">
    <div class="card">
      <router-view />
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
import Navbar from "./components/Navbar";
export default {
  components: {
    Navbar,
  },
  methods: {
    ...mapActions(["cargarLocalStorage"]),
  },
  created() {
    this.cargarLocalStorage();
  },
};
</script>

<style scoped>
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  background-color: #fafafa;
  padding: 25px 25px;
  margin: 25px 25px;
  border: 1px solid #dbdbdb !important;
  border-radius: 5px !important;
}
</style>
