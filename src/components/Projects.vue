<template>
<div class="row">

    <!--info div started-->
    <div class="col-md-8 offset-md-2 col-sm-12">


 <div class="row">

      <div class="col-md-4 " v-for="(repo,index) in repos" :key="index">
      <a v-bind:href=repo.html_url>
        <div class="card" >
          <div class="card-body">
            <h5 class="card-title" >{{repo.name}}</h5>
            <p class="card-text">{{repo.description}}</p>
            <h6 class="card-subtitle mb-2 text-muted">Language: {{repo.language}}</h6>
            <p class="card-text">Stars {{repo.stargazers_count}}   <span class="float-right">forks {{" " + repo.forks_count}}</span></p>
            
            <div class="text-center">
              <a v-bind:href=repo.homepage class="btn btn-primary" style="width: 60%; margin-top: 20px;">website</a>
            </div>
            
          </div>
        </div>
        </a>
        
      </div>


    </div>

    <!--div ends-->
    </div>
    </div>

</template>

<script>

export default {
  name: 'Projects',
  data(){
    return {

    };
  },
  props:['repos']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

    a{
      text-decoration: none;
      color:#263238;
    }
    .card{
      margin-top: 25px;
    }
    
    .btn{
        background-color: rgb(59, 17, 128);
        color: white;
        width: auto;
    }
</style>
