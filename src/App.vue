<script setup>
 import {ref} from 'vue'
// ####################################### factorial #####################################
//   let numberRef = ref(0);

//   let aux = ref(0);

// function doClick(){

//  aux.value = numberRef.value

// }

// function calculateFactorial(numberRef){

//   let total =1;

//   for(let i=1; i <= numberRef; i++){
//     total *= i;
//   }

//   return total;

// }



// ################################################### tarejeta de invitación ################################################# -->
  
  // let name=ref ('')
  // let apellido=ref ('')
  // let fecha=ref ('')
  // let numero=ref ('')
  // let fechaf
  // function calcularEdad(){
  //   const fechaActu=new Date()
  //   const fechai=new Date(fecha.value)
  //   fechaf=Math.floor((fechaActu-fechai)/31536000000)
  //   return fechaf
  // }
  // ################################################### parqueadero ########################################################### -->
 let listParqueadero=[{placa:1,categoria:'motocicleta', tiempo:15,   actu:true},
                      {placa:2,categoria:'automovil',   tiempo:45,   actu:false},
                      {placa:3,categoria:'pesado',      tiempo:30,   actu:false}]
  
 const valorMoto=1000;
 const valorPesado=2000;
 const valorAuto=2000;
 let total=0
function pesado(){
  total+=valorPesado
 
}
function moto(){
  total+=valorPesado
  
}
function carro(){
  total+=valorPesado
  
}
  // function total(categoria){
  //   let total=0
  //   if(categoria=='pesado'){
  //     return total+= valorPesado
  //   }else if(categoria=='automovil'){
  //     return total+= valorAuto
  //   }else{
  //     return total+=valorMoto
  //   }
  // }
</script>
<template>
   <!--  ################################################### parqueadero ########################################################### --> 
   <div>
    <div v-for="(newcar,i) in listParqueadero" :key="i" class="newcar">
      <ul>
        <li>{{newcar.placa}}</li>
        <li>{{newcar.categoria}}</li>
        <li>{{newcar.tiempo}} minutos</li>
        <li v-if="newcar.actu">dentro</li>
        <li v-else>salio</li>
      </ul>
    </div>
    <div class="listSalio">
      <p>lista de carros que salieron</p>
      <div v-for="(newcar,i) in listParqueadero" :key="i">
        <ul v-if="!newcar.actu">
          <li> placa: {{newcar.placa}} </li>
         <div v-if="newcar.categoria=='pesado'">  <!--El total hasta ahora es: {{ total+=valorPesado }} -->{{ pesado() }}</div>
          <div v-else-if="newcar.categoria=='automovil'"><!--El total hasta ahora es: {{ total+=valorAuto }} -->{{ carro() }}</div>
          <div v-else><!--El total hasta ahora es: {{ total+=valorMoto }}{{ pesado }}-->{{ moto() }}</div>
        </ul>
      </div>
      <h1>total {{ total }}</h1>
    </div>
  </div>
  <!-- ################## tarejeta de invitación ###################### -->

 <!-- <div>
  <input v-model="name" type="text" placeholder="ingrese su nombre">
  <input v-model="apellido" type="text" placeholder="ingrese su apellido">
  <input v-model="fecha" type="date">
  <input v-model="numero" type="text" placeholder="ingrese su numero">
 </div>

 <div class="tarjeta">
  <h1 >{{ name }}</h1>
  <h1>{{ apellido }}</h1>
  
  <h1 class="acom" v-if="calcularEdad()!=null && calcularEdad()>=18">{{ calcularEdad() }}</h1>
  <h1 v-if="calcularEdad()<18  && calcularEdad()!=null">requiere acompañante</h1>

  <h1>{{ numero }}</h1>

 </div> -->
  <!-- ################################################# factorial ########################################## -->
  <!-- <div>

    <input v-model="numberRef" type="number">
    <button @click="doClick()">presioname</button>
      <h1>{{ calculateFactorial(aux) }}</h1>
    
  </div> -->


 




</template>





 
<style>
/* <!-- ################## tarejeta de invitación ###################### -->  */
/* .tarjeta{
  background-color: aqua;
}
.acom{
  background-color: blue;
} */
</style>
