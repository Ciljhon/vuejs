<template>
  <h1>{{titulo}}</h1>

  <div class="row">
    <div class="col-md-4">
      <h1>Nueva Actiividad</h1>
      <form >
        <label for="">Ingrese Titulo</label>
        <input type="text" class="form-control" v-model="act.titulo">

        <label for="">Ingrese Detalle</label>
        <textarea class="form-control" v-model="act.detalle"></textarea>
        <br>
        <button type="button" class="btn btn-success float-right" @click="guardarAct()">Guardar Actividad</button>
      </form>
      {{act}}
    </div>

    <div class="col-md-8">
      <h1>List de Actividades</h1>
      <table class="table table-striperd table-hover">
        <tr>
          <td>ID</td>
          <td>NOMBRE</td>
          <td>DETALLE</td>
          <td>ACCIONES</td>
        </tr>

        <tr v-for="(actividad, index) in actividades" :key="index">
          <td>{{index}}</td>
          <td>{{actividad.titulo}}</td>
          <td>{{actividad.detalle}}</td>
          <td>
        <button class="btn btn-outline-primary btn-xs" @click="enproceso(actividad)">EMPEZAR</button>
        <button class="btn btn-danger btn-xs" @click="eliminarAct(index)">ELIMINAR</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
   <br>

    <div class="row ">
      <div  class="col-md-4 bg-warning text-light">
        <h3>EN PROCESO</h3>
      <div class="card bg-danger" v-for="(a, index) in actividades" :key="index">
        <div class="titulo" v-if="a.estado === 1">
          <h1>{{a.titulo}}</h1>
        </div>
      </div>
    </div>
      <div  class="col-md-4 bg-success text-light"><h3>FINALIZADO</h3>
      </div>
      <div  class="col-md-4 bg-danger text-light"><h3>CANCELADO</h3>
      </div>
    </div>

 

  
<br>


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
      actividades:[],
      act:{titulo:"",detalle:"", estado:0}
    }
  },
  methods:{
    aumentar(){
      this.numero++;

    },
    reducir(){
      this.numero--;
    },
      guardarAct(){
        var aux=this.act
        this.reset();
        this.actividades.push(aux)
      },
      reset(){
         this.act = {titulo:"", detalle:""}
      },
      eliminarAct(posicion){
        this.actividades.splice(posicion, 1);
      },
      enproceso(actividad){
        actividad.estado = 1;
      },
      finalizado(actividad){
        actividad.estado = 2;
      },
      cancelado(actividad){
        actividad.estado = 3;
      }
    }
  }
</script>

<style>

</style>