<template>
  <div id="app">
   
   
<div class="cal">
   <img alt="Vue logo" src="./assets/calc.jpg">
    <HelloWorld msg="Calculadora"/><br>
    <label for="app">numero 1</label>
     <input type="Number" v-model="numero1" placeholder=" ingrese numero1"   ><br><br>
     
     <label for="">numero 2</label>
     <input type="Number"  v-model="numero2" placeholder=" ingrese numero2"><br><br>
   <label for=""> Operacion:</label>
     <select v-model="selected" > 
  <option :value="{}" disabled hidden> Seleccione</option>
 <option v-for="option in options" :value="option" :key="option.id" >
    {{ option.name }}
  </option>
</select>
     <button @click="validar()" > Calcular </button>

     <h2>resultado: {{+""+resultado}}</h2>


    </div>

    <div class="container">
        <ComponentTabla :array="array"  />
    </div>
   

  </div>
</template>

<script>

import HelloWorld from './components/HelloWorld.vue'
import ComponentTabla from './components/ComponentTabla.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    ComponentTabla
},
  data:()=>({
  
    numero1:'',
    numero2:'',
    resultado:0,
    options: [
       { id: 1, name: 'suma' },
        { id: 2, name: 'resta' },
         { id: 3, name: 'multiplicacion' },
          { id: 4, name: 'division' },
         
      
    ], 
    selected:{},
    array:[],
    
   
    
   
  }),
  methods:{
    calcular(){
     
      if(this.selected.id===1){
       this.resultado= Number(this.numero1)+ Number(this.numero2)
      }else 
        if(this.selected.id===2){
            this.resultado= Number(this.numero1)- Number(this.numero2)
        }else
        if(this.selected.id===3){
           this.resultado= Number(this.numero1)* Number(this.numero2)
        }
        else{
           this.resultado= Number(this.numero1)/ Number(this.numero2) 
           }

           this.llenarTabla()
        },

      llenarTabla(){
        this.array.push({op:this.selected.name,n1:this.numero1,n2:this.numero2,rs:this.resultado})

      },
     validar(){
      
      
        if(this.numero1 ==='' || this.numero2 ===''){
           alert("datos requeridos")  
      } else 
           this.calcular();
            
      
     

     }

  }
    
 }  

  

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}

input,select{
  margin:  3px;
  border: 2px solid #42b983;
  border-radius: 3px;
  background-color: #fff;
  padding: 5px;
  text-size-adjust: 5px;
}
label{
  border-radius: 2px;
  text-decoration-color: black;
  text-anchor: middle;
  margin:  5px;
  padding: 5px;
}

button{
   border: 2px solid #42b983;
  border-radius: 3px;
  background-color: #fff;
  text-align: center;
  font-size: medium;
  text-decoration-color: #42b983;
  padding: 10px;
}
img{
  height: 200px;
  width: 320px;

}

.container{
  
  margin-top: 5px;
  justify-content: center;
}

</style>
