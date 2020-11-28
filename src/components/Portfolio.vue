<template>
    <!--whole body container for padding-->
    <div class="container">

        <!--row for grid for image and bio-->
        <div class="row">

            <!--users image container-->
            <div class="col-md-4 col-sm-12 text-center">
                <img v-bind:src=profile.avatar_url alt="">
            </div>

            <div class="col-md-8 col-sm-12">

            

                <h2 style="margin-top: 5%;">
                    Hi. I'm <b class="name "> {{profile.name}}.</b>
                  </h2>
                  <h5 style="margin-top: 5%;padding: 10px;">
                    {{profile.bio}}  
                  </h5>

                  <!--social media handles-->
                    <div class="col-md-6  col-sm-12">
                        <h5 style="margin-top: 5%;">Follow me :</h5>
                            <a
                                v-bind:href=profile.html_url
                                target="_blank"
                                rel="noopener noreferrer"
                                ><i class="fa fa-github-square social"></i
                            ></a>
                            <a
                                v-bind:href=profile.twitter_username
                                target="_blank"
                                rel="noopener noreferrer"
                                ><i class="fa fa-twitter-square social"></i
                            ></a>
                            <a
                            v-bind:href=profile.email
                            target="_blank"
                            rel="noopener noreferrer"
                            ><i class="fa fa-envelope social"></i
                        ></a>
                    </div>

 
                        <div class="container">
                            <h5 style="margin-top: 5%;">Your Link : <a v-bind:href = url>{{url}}</a></h5>  
                        </div>
                    
                <hr>
                        
            <!--bio colums end-->
            </div>

        <!--row ends-->
        </div>
        
                <!--row for address-->
                <div class="row">

                    <!--info div started-->
                    <div class="col-md-8 offset-md-4 col-sm-12">
                       
                        <div class="container">
                            <h3>Personal information</h3>
                            <br>
                            <h5><i class="fa fa-home" style="font-size: 30px;margin-right: 30px;"></i>  {{profile.location}}.</h5>
                            <h6><i class="fa fa-building" style="font-size: 30px; margin-right: 30px;"></i>{{profile.company}}</h6>
                            <h6><i class="fa fa-external-link" style="font-size: 30px; margin-right: 30px;"></i><a v-bind:href= profile.blog style="text-decoration:none;font-size:20px" > {{profile.blog }}</a></h6>
                 
                        </div>
                    <!--info div ends end-->
                    </div>
        
                <!--row ends-->
                </div>

                <hr>
                
                <Projects v-bind:repos="repos"></Projects>
                
                








    <!--container class ends-->
    </div>
</template>

<script>
import Projects from './Projects.vue'

export default {
  name: 'Portfolio',
  components: {
    Projects
  },
  data(){
    return{
        
    };
  },
  props:['profile','repos','url'],
  methods: {
      
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
        img{
            width: 85%;
            height: 85%;
            border-radius: 50%;
        }
        .row{
            margin-top: 50px;
        }
        .social{
        width: 23%;
        font-size: 50px;
        color: #04316b;
      }
      .social:hover:not(.active) {
        color:  #04316b;
        font-size: 60px;
      }
      .follow a{
          font-size: 25px;
          text-decoration: none;
      }
      .btn{
          width: 60%;
          margin: 5% 18% 5% 18%;
          font-size: 25px;
      }
</style>
