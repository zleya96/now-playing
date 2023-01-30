<template>
  <div>
    <h1>Now Playing</h1>
    <table id="datatable" class="table table-hover dt-responsive">
      <thead>
        <tr>
          <th><h3 class="grow">Title</h3></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="result in results.results" :key="result.id" >
          <td><div class="grow">{{ result.title }}</div></td>
        </tr>
      </tbody>
    </table>
  </div>
  
</template>
 
<script>
import "jquery/dist/jquery.min.js";
import "bootstrap/dist/css/bootstrap.min.css";
import "datatables.net-dt/js/dataTables.dataTables";
import "datatables.net-dt/css/jquery.dataTables.min.css";
import $ from "jquery";

export default {
  mounted() {
    fetch("https://api.themoviedb.org/3/movie/now_playing?api_key=1219113bb7f0eec0cf17bfe1ea256ebb&language=en-US&page=1")
      .then((response) => response.json())
      .then((data) => {
        this.results = data;
        setTimeout(() => {
          $("#datatable").DataTable({
            lengthMenu: [
              [5,10, 25, 50, -1],
              [5,10, 25, 50, "All"],
            ],
            pageLength: 5,
          });
        });
      });
  },
  data: function () {
    return {
      results: [],
    };
  },
};
</script>