<script>
import axios from 'axios';
export default {
  data() {
    return {
      projects: [],
    }
  },
  methods:{
        getData(){
        axios.get('http://127.0.0.1:8000/api/projects')
          .then(response => {
          this.projects = response.data.response;
          console.log(response.data.response);
          })
          .catch(function (error) {
          // handle error
          console.log(error);
          })
          .finally(function () {
          // always executed
          })
      },
  },
  created(){
    this.getData();

  }
}
</script>

<template>
<h1>Helloooooo</h1>
<div class="div" v-for="project in projects">
  <h1>{{ project.name }}</h1>
</div>
</template>

<style >
</style>