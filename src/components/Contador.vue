
<template>
  <h2>{{ titulo }}</h2>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputed }}</p>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputed }}</p>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputed }}</p>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputed }}</p>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputed }}</p>

  <div>
    <button v-on:click="incrementar()">+1</button>
    <button v-on:click="decrementar()">-1</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero: 10,
      titulo: "Contador",
    };
  },
  methods: {
    calcularCuadrado() {
      console.log("Entro a Calcular");
      return this.numero * this.numero;
    },
    incrementar() {
      this.numero++;
    },
    decrementar() {
      this.numero--;
    },
  },
  computed: {
    calcularCuadradoComputed() {
      console.log("Entro a Calcular computado");
      return this.numero * this.numero;
    },
  },
};
</script>

<style>
button {
  background: #64b687;
  border-radius: 5px;
  margin: 0px 10px;
  border: 1px solid white;
  color:white;
  cursor: pointer;
  padding: 5px 20px;
}
button :hover {
 background: #5aa67b;
}
</style>
