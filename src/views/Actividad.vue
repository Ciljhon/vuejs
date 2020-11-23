<template>
  <h1>{{titulo}}</h1>
  <h4>Cantidad de Actividades:{{numero}}</h4>
  <input type="text" v-model="numero">
  <button @click="aumentar">+</button>
  <button @click="reducir">-</button>
  <hr>
  {{nombre}}
  <ol>
    <li v-for="nom in nombre" :key="nom">{{nom}} </li>
  </ol>
</template>

<script>
export default {
  data(){
    return{
      titulo: "ACTIVIDADES",
      numero: 14,
      nombre:["Juan","Cristisn","jhonnyce","jael"],

    }
  },
  methods:{
    aumentar(){
      this.numero++;

    },
    reducir(){
      this.numero--;

    }
  }

}
</script>

<style>

</style>