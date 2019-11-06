<template>
  <div id="app">
    <p>
      {{ valor }}
    </p>
    <button @click="increment">Incrementar</button>
    <br><hr>
      <input type="text" v-model="evento">
    </p>
    <div v-show="aberto">
      <h1 v-bind:class="color">{{ evento }}</h1>
    </div>
    <div>
      <button @click="trocar">Trocar</button>
    </div>
    <hr>
    <ul>
      <li v-for="(linguagem, index) in linguagens" :key="index">{{linguagem}}</li>
    </ul>

    <input type="text" v-model="lang">
    <button @click="add_language">Adicionar linguagem</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      evento: "Sacomp" + " 2019",
      color: "red",
      aberto: false,
      valor: 0,
      linguagens: ['Javascript', 'Java', 'PHP', 'C#', 'Python'],
      lang: null
    };
  },

  methods: {
    trocar() {
      this.aberto = !this.aberto;
    },
    increment() {
      this.valor++;
    },
    add_language(){
      this.linguagens.push(this.lang);
      this.lang = null;
    }
  }
};
</script>

<style>
.red {
  background: red;
}
</style>
