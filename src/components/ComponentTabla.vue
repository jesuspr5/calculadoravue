<template>
    <div class="table">


        <table>
      <thead>
        <tr>
          <th> operacion</th>
          <th> numero1</th>
          <th> numero2</th>
          <th> resultado</th>
        </tr>

      </thead>
      <tbody v-for="item in array" :value="item" :key="item.id">
        <tr>
          <th>{{item.op}}</th>
          <th>{{item.n1}}</th>
          <th>{{item.n2}}</th>
          <th>{{item.rs}}</th>
         

        </tr> 
      </tbody> 

    </table>
    
    </div>
</template>

<script>
export default{
     name:'ComponentTabla' ,
     props:{
      array:[]
     }
 
}
</script>

<style>
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