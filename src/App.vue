<script>
import axios from "axios";
export default {
  data() {
    return {
      conselho: {
        slip: {
          advice: "",
        },
      },
    };
  },
  methods: {
    async Buscar() {
      this.id = Math.floor(Math.random() * 99 + 1);
      const url = `https://api.adviceslip.com/advice/${this.id}`;
      const { data } = await axios.get(url);
      this.conselho = data;
    },
  },
};
</script>
<template>
  <body>
    <div class="conselho">
      <p>{{ this.conselho.slip.advice }}</p>
    </div>

    <button @click="Buscar">Aconselhar</button>
  </body>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=IBM+Plex+Serif:wght@100&display=swap");

* {
  font-family: "IBM Plex Serif", serif;
}

div {
  font-size: 50px;
}

button {
  border-radius: 45px;
  height: 60px;
  width: 180px;
  border-color: transparent;
}
</style>
