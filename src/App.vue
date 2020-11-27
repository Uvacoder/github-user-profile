<template>


  <Portfolio v-on:showproject="showproject"/>
  <Projects v-bind:repos="repos" v-show="showProj"/>
  <Input v-on:changerepo="getrep($event)"/>

</template>

<script>

import Input from './components/Input.vue'
import Portfolio from './components/Portfolio.vue'
import Projects from './components/Projects.vue'

export default {
  name: 'App',
  components: {
    Input,
    Portfolio,
    Projects
  },
  data(){
    return{
      username: "",
      repos: {},
      showProj: false
    };
  },
  methods: {
      showproject: function(){
        this.showProj = !this.showProj;
        console.log(this.showProj);
      },
      getrep: async function(newRepo){
        this.username = newRepo;
        const url = "https://api.github.com/users/" + this.username + "/repos"
        const response = await fetch(url)
      
        this.repos = await response.json();
        console.log(this.repos);

      }
  },
  async created(){
      
      const url = "https://api.github.com/users/" + this.username + "/repos"
      const response = await fetch(url)
      
      this.repos = await response.json();
      await console.log(this.repos);

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
}
</style>
