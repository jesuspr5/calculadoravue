<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Calculadora"/>
    
    <label for="">numero1</label>
     <input v-model="numero1" placeholder=" ingrese numero1"><br><br>
     
     <label for="">numero2</label>
     <input v-model="numero2" placeholder=" ingrese numero2"><br><br>
   
     <select v-model="selected" > 
  
 <option v-for="option in options" :value="option" :key="option.id" >
    {{ option.name }}
  </option>
</select>
     <button @click="calcular()" > Calcular </button>

     <h2>{{resultado}}</h2>

    <table>
      <thead>
        <tr>
          <th> id</th>
          <th> numero1</th>
          <th> numero2</th>
          <th> resultado</th>
        </tr>

      </thead>
      <tbody>
        <tr>
          <td>{{}}</td>
          <td>{{numero1}}</td>
          <td>{{numero2}}</td>
          <td>{{resultado}}</td>

        </tr> 
      </tbody> 

    </table>
    

  </div>
</template>

<script>

import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },

  data:()=>({
  
    numero1: '',
    numero2: '',
    resultado:0,
    options: [
       { id: 1, name: 'suma' },
        { id: 2, name: 'resta' },
         { id: 3, name: 'multiplicacion' },
          { id: 4, name: 'division' },
      
    ], 
    array:[]
   
    
   
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
           this.resultado= Number(this.numero1)/ Number(this.numero2) }
        },

       
      

        
  }, 
  computed:{
   
    },
    mounted:{
      
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
  margin-top: 60px;
}

table {
  border: 2px solid #42b983;
  border-radius: 3px;
  background-color: #fff;
  text-align: center;
}

th {
  background-color: #42b983;
  color: rgba(255,255,255,0.66);
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

td {
  background-color: #f9f9f9;
}

th, td {
  min-width: 120px;
  padding: 10px 20px;
}
th.active {
  color: #fff;
}

th.active .arrow {
  opacity: 1;
}

.arrow {
  display: inline-block;
  vertical-align: middle;
  width: 0;
  height: 0;
  margin-left: 5px;
  opacity: 0.66;
}

.arrow.asc {
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-bottom: 4px solid #fff;
}

.arrow.dsc {
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-top: 4px solid #fff;
}

</style>
