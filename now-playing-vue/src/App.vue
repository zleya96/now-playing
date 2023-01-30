<template>
  <div class="container">
    <DataTable/>
  </div>
</template>

<script>
import DataTable from './components/DataTable'

export default {
  name: 'App',
  components: {
    DataTable
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  margin-top: 60px;
  
}
.container {
    max-width: 1000px;
  }
#datatable th {
  text-align: center;
}
#datatable {
  color: #000000;
}
.grow { 
transition: all .2s ease-in-out; 
}
.grow:hover { 
transform: scale(1.1); 
}
body {
  min-height: 100vh;  
  background-color: #FFE53B;  
  background-image: linear-gradient(180deg, #ffe53ba8 0%, #ff404090 100%);  
}
</style>
