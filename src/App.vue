<template>


  <Portfolio  v-if="showprof" v-bind:profile="profile" v-bind:repos="repos"/>
  <Input v-on:changerepo="getrep($event)"/>

</template>

<script>

import Input from './components/Input.vue'
import Portfolio from './components/Portfolio.vue'

export default {
  name: 'App',
  components: {
    Input,
    Portfolio
  },
  data(){
    return{
      username: "",
      repos: {},
      profile: {},
      showprof: false
    };
  },
  methods: {
      getrep: async function(newRepo){
        const url = "https://api.github.com/users/" + newRepo;
        const profData = await fetch(url);
        const response = await fetch(url + "/repos");
        
        
        this.profile = await profData.json();
        this.repos = await response.json();
        this.showprof = true;

      }
  },
  async created(){
      
      
      const url = "https://api.github.com/users/" + this.username;
      const response = await fetch(url + "repos");
      const profData = await fetch(url);
      
      this.profile = await profData.json();
      this.repos = await response.json();

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  margin-bottom: 90px;
}
</style>
