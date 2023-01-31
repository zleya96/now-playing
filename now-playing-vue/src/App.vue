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
  opacity: 100%;
}

.modal-title {
  font-weight: bold;
}

/* .modal-body {
  background-image: url("../src/assets/movie-theater.jpg");
} */
.table-poster {
  max-width: 20%;
  height: auto;
}

#main-title {
  margin-bottom: 20px;
}

#modal-background {
  background-image: url('https://image.tmdb.org/t/p/original');
  background-size: 225%;
  background-position: center;
}
</style>
