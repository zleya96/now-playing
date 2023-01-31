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

.table-poster {
  max-width: 20%;
  height: auto;
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
</style>
