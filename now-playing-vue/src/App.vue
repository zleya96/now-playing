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
@import url('https://fonts.googleapis.com/css2?family=Limelight&display=swap');

#app {
  font-family: 'Limelight', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffda1f;
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
  color: #ffda1f;
}

select {
  color: #ffda1f;
}

input {
  color: #ffda1f;
}

.grow {
  transition: all .2s ease-in-out;
}

.grow:hover {
  transform: scale(1.1);
}

body {
  min-height: 100vh;
  background-image: linear-gradient(180deg, #000b51da 0%, #590101db 100%);
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
  color: black;
}

.modal-title {
  font-weight: bold;
}

#main-title {
  margin-bottom: 20px;
  font-size: 72px;
}

#modal-background {
  background-size: 300%;
  background-position: center;
}

.modal-content {
  background-color: hsla(0, 0%, 100%, 0.1);
  font-family: 'Courier New', Courier, monospace;
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
  margin:2vh 5vw;
}

#tab-title {
  margin-bottom: 20px;
}

#datatable td { 
  border-top: none;
  border-bottom: none;
} 

#datatable thead th{ 
  border-top: none;
  border-bottom: none;
}

#datatable { 
  border-top: none;
  border-bottom: none;
  margin-bottom: 15px;
}

#datatable tbody :hover{
  color: rgba(105, 192, 255, 0.877);
}

#datatable_info {
  color: #ffda1fa5;
  font-weight: bold;
}

#datatable_paginate {
  color: rgba(105, 192, 255, 0.877);
  font-weight: bold;
}
</style>
