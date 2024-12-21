
<template>
  <h2>{{ encabezado }} : {{ valor2 }}</h2>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputed }}</p>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputed }}</p>
  <!--   <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputed }}</p>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputed }}</p>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputed }}</p> -->

  <div>
    <button @:click="incrementar()">+1</button>
    <button v-on:click="decrementar()">-1</button>
  </div>
  <div v-if="esVerdad">
    <h1>Feliz Navidad</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero: this.valor,
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
  //Primera forma de declaracion de un props
  //props:['encabezado','valor']
  props: {
    encabezado: {
      type: String,
      validator(value) {
        return value.includes("a");
      },
    },
    valor: Number,
    valor2: {
      type: Number,
      required: false,
      default: 77,
      validator(value) {
        //programo mi validacion bajo mi criterio y retorno tru
        // cuando es valido para mi
        // y retorno false cuando no es valido para mi
        return value <= 77;
      },
    },
    esVerdad: {
      type: Boolean,
      required: true,
    },
    arreglo: {
      type: Array,
    },
    fecha: Date,
    objetoPersona: Object,
  },
};
</script>

<style>
button {
  background: #64b687;
  border-radius: 5px;
  margin: 0px 10px;
  border: 1px solid white;
  color: white;
  cursor: pointer;
  padding: 5px 20px;
}
button:hover {
  background: #5aa67b;
}
</style>
