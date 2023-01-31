<template>
  <div>
    <div class="modal fade" id="movie-modal" tabindex="-1" aria-labelledby="movie-modal-Label" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content" id="modal-background">
          <div class="modal-header">
            <h5 class="modal-title" id="movie-modal-label"></h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div  class="modal-body">
            <img class="modal-poster" v-bind:src="'https://image.tmdb.org/t/p/original' + movie.poster_path" alt="">
            <p><b>Title: </b>{{ movie.title }}</p>
            <p><b v-for="genre in genres" :key="genre.id">{{ genre }}</b></p>
            <p><b>Overview: </b>{{ movie.overview }}</p>
            <p id="movie-release"></p>
            <p><b>Runtime: </b>{{ movie.runtime }} minutes</p>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-primary" data-bs-dismiss="modal">Close</button>
          </div>
        </div>
      </div>
    </div>

    <h1 id="main-title">Now Playing</h1>
    <table id="datatable" class="table table-hover dt-responsive">
      <thead>
        <tr>
          <th>&nbsp;</th>
          <th >
            <h3 @click="toggleABC" class="grow" v-if="abc">A - Z</h3>
            <h3 @click="toggleABC" class="grow" v-else>Z - A</h3>
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="result in results.results" :key="result.id" data-bs-toggle="modal" data-bs-target="#movie-modal"
          @click="setMovie(result.id)">
          <td><img class="table-poster" v-bind:src="'https://image.tmdb.org/t/p/original' + result.poster_path" alt="">
          </td>
          <td>
            <div class="grow">{{ result.title }}</div>
          </td>
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
import 'bootstrap/js/dist/modal'

export default {
  created() {
    fetch("https://api.themoviedb.org/3/movie/now_playing?api_key=1219113bb7f0eec0cf17bfe1ea256ebb&language=en-US&page=1")
      .then((response) => response.json())
      .then((data) => {
        this.results = data;
        setTimeout(() => {
          $("#datatable").DataTable({
            lengthMenu: [
              [5, 10, 25, 50, -1],
              [5, 10, 25, 50, "All"],
            ],
            "order": [[1, 'asc']],
            pageLength: 5,
          });
        });
      });
  },
  methods: {
    setMovie(id) {
      fetch("https://api.themoviedb.org/3/movie/" + id + "?api_key=1219113bb7f0eec0cf17bfe1ea256ebb&language=en-US")
        .then((response) => response.json())
        .then((data) => {
          this.movie = data;
          this.formatDate(data);
          this.setBackground(data);
          this.setGenres(data);
        });
    },
    formatDate(data) {
      let date = new Date(data.release_date);
      let year = date.getFullYear();
      let month = date.getUTCMonth() + 1;
      let day = date.getDate();
      document.getElementById('movie-release').innerHTML = "<b>Released: </b>" + month + "/" + day + "/" + year;
    },
    setBackground(data) {
      const baseURL = "https://image.tmdb.org/t/p/original";
      let path = data.backdrop_path;
      document.getElementById('modal-background').style.backgroundImage = `url(${baseURL}${path})`
    },
    setGenres(data) {
      let g = data.genres;
      let result = [];
      for(let i = 0; i < g.length - 1; i++) {
        result[i] = g[i].name + ", "
      }
      result[g.length - 1]  = g[g.length - 1].name;
      this.genres = result;
    },
    toggleABC() {
      if(this.abc === true) {
        this.abc = false;
      } else {
        this.abc = true;
      }
    }
  },
  data: function () {
    return {
      results: [],
      movie: {},
      genres: [],
      abc: true,
    };
  },
};
</script>