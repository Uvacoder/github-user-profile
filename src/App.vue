<template>

  <div>
      <div id="mybutton">
        <i class="fa fa-chevron-circle-up feedback"></i>
      </div>

      <div style="text-align:center;">
        <button v-if="!showprof" class="btn btn-success" v-on:click="getrep($route.params.id)" >Show profile</button>
      </div>
      
      <Portfolio v-if="showprof"  v-bind:profile="profile" v-bind:repos="repos" v-bind:url="url"/>
      <Input v-on:changerepo="getrep($event)"/>

  </div>


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
      showprof: false,
      url: "https://kashif.fail/"
    };
  },
  methods: {
      getrep: async function(newRepo){

        console.log(newRepo)
        const url = "https://api.github.com/users/" + newRepo
        const profData = await fetch(url);
        const response = await fetch(url + "/repos");
        this.username = newRepo
        
        this.profile = await profData.json();
        this.repos = await response.json();
        this.url =  await this.url + newRepo
        this.showprof = await  !this.showprof;
      }
  },
  async created(){
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

.feedback {
  background-color : #31B0D5;
  color: white;
  border-color: #04316b;
  padding: 10px;
  border-radius: 30%
}

#mybutton {
  position: fixed;
  bottom: 15px;
  right: 15px;
  font-size:50px;
  z-index: 2;
}
</style>
