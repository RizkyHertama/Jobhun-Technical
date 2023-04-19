<template>
   
      <h1>Movie List</h1>
      
      <div class="form-group mt-5">
            <input type="text" class="form-control" placeholder="Search movies" v-model="searchTerm" @input="filterMovies">
        </div>

      <div class="container-fluid blogs pt-5 pb-5">
        <div class="container">
          <div class="row pt-4 gx-4 gy-4">
            <div class="col-md-4" v-for="show in showsToDisplay" :key="show.id">
              <div class="card">
                <img :src="show.image.medium" alt="show.name">
                <div class="card-body">
                  <h4>{{ show.name }}</h4>
                </div>
              </div>
            </div>
          </div>
  
          <nav v-if="totalPages > 1">
            <ul class="pagination">
              <li class="page-item" :class="{ disabled: currentPage === 1 }">
                <a class="page-link" href="#" @click.prevent="changePage(currentPage - 1)">Previous</a>
              </li>
              <li class="page-item" v-for="page in totalPages" :key="page" :class="{ active: currentPage === page }">
                <a class="page-link" href="#" @click.prevent="changePage(page)">{{ page }}</a>
              </li>
              <li class="page-item" :class="{ disabled: currentPage === totalPages }">
                <a class="page-link" href="#" @click.prevent="changePage(currentPage + 1)">Next</a>
              </li>
            </ul>
          </nav>

  
        </div>
      </div>

  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        shows: [],
        currentPage: 1,
        itemsPerPage: 6,
        totalItems: 0,
        searchTerm: '',
      };
    },
  
    async mounted() {
      try {
        const response = await axios.get('http://api.tvmaze.com/search/shows?q=girls');
        this.shows = response.data.map(data => data.show);
        this.totalItems = this.shows.length;
      } catch (error) {
        console.error(error);
      }
    },
  
    computed: {
      totalPages() {
        return Math.ceil(this.totalItems / this.itemsPerPage);
      },
      showsToDisplay() {
        const startIndex = (this.currentPage - 1) * this.itemsPerPage;
        const endIndex = startIndex + this.itemsPerPage;
        return this.shows.filter(show => show.name.toLowerCase().includes(this.searchTerm.toLowerCase())).slice(startIndex, endIndex);
      },
    },
  
    methods: {
      changePage(page) {
        if (page < 1 || page > this.totalPages) return;
        this.currentPage = page;
      },
      filterMovies() {
        this.currentPage = 1;
        this.totalItems = this.shows.filter(show => show.name.toLowerCase().includes(this.searchTerm.toLowerCase())).length;
      },
    },
  };
  </script>
  
  <style scoped>
  h1{
    display: flex;
    justify-content: center;
  }
  
  .card img {
    width: auto;
    height: auto;
  }

  .form-group{
    width: 50%;
    display: flex;
    justify-content: center;
    margin: auto;
  }

  .pagination{
    margin-top: 3%;
    gap: 0.5rem;
  }

  </style>
  