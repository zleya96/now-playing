<template>
  <div>
    <div class="container">
      <DataTable />
    </div>
  </div>
</template>

<script>
import DataTable from './components/DataTable'

export default {
  name: 'App',
  components: {
    DataTable,
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
  margin-bottom: 60px;
}

.container {
  max-width: 75%;
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
  background-image: linear-gradient(180deg, #fdee8bda 0%, #ff4040ae 100%);
}

.modal-poster {
  max-width: 50%;
  height: auto;
}

.modal-body p {
  text-align: left;
}

.modal-body {
  background-color: hsla(0, 14%, 81%, 0.791);
}

.modal-title {
  font-weight: bold;
}

#main-title {
  margin-bottom: 20px;
}

#modal-background {
  background-size: 300%;
  background-position: center;
}

.modal-content {
  background-color: hsla(0, 0%, 100%, 0.1);
}

.table-poster {
  max-width: 30%;
  height: auto;
  border:solid 2vmin rgb(140, 93, 46);
  border-bottom-color:rgb(70, 47, 23);
  border-left-color:rgb(140, 93, 46);
  border-radius:2px;
  border-right-color:rgb(140, 93, 46);
  border-top-color:rgb(70, 47, 23);
  box-shadow:0 0 5px 0 rgba(0,0,0,.25) inset, 0 5px 10px 5px rgba(0,0,0,.25);
  box-sizing:border-box;
  display:inline-block;
  margin:3vh 5vw;
}

#datatable td { 
  border-top: none;
  border-bottom: none;
} 

#datatable thead th{ 
  border-top: none;
  border-bottom: none;
}
</style>
