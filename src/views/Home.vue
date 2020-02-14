<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <hr>
    <div v-for="cup in cups">
      <h2> {{ cup.material }}</h2>
      <h2> {{ cup.size }}</h2>
      <h2> {{ cup.color }}</h2>
      <hr>
    </div>

  </div>
</template>

<style>
</style>

<script>
import axios from "axios";
export default {
  data: function() {
    return {
      message: "Cups!",
      cups: []
    };
  },
  created: function() {
    axios.get("/api/cups").then(response => {
      this.cups = response.data;
    });
  },
  methods: {}
};
</script>