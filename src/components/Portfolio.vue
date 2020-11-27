<template>
    <!--whole body container for padding-->
    <div class="container">

        <!--row for grid for image and bio-->
        <div class="row">

            <!--users image container-->
            <div class="col-md-4 col-sm-12 text-center">
                <img src="https://avatars2.githubusercontent.com/u/43416961?v=4" alt="">
            </div>

            <div class="col-md-8 col-sm-12">
                <h2 style="margin-top: 5%;">
                    Hi. I'm <b class="name "> Kashif Ahmad.</b>
                  </h2>
                  <h5 style="margin-top: 5%;padding: 10px;">
                    A Focused and enthusiastic  <b>Full Stack Developer</b> with a keen interest in 
                    web and android development and solving DSA problems. 
                    I am a passionate individual who thrives to build and apply algorithms to solve real-world industry problems. 
                    worked on various technologies like git, cloud, devops, etc.  
                  </h5>

                  <!--social media handles-->
                    <div class="col-md-6  col-sm-12 animate__animated animate__bounceInLeft">
                        <h5 style="margin-top: 5%;">Follow me :</h5>
                            <a
                                href="#"
                                target="_blank"
                                rel="noopener noreferrer"
                                ><i class="fa fa-github-square social"></i
                            ></a>
                            <a
                                href="#"
                                target="_blank"
                                rel="noopener noreferrer"
                                ><i class="fa fa-twitter-square social"></i
                            ></a>
                            <a
                            href="#"
                            target="_blank"
                            rel="noopener noreferrer"
                            ><i class="fa fa-envelope social"></i
                        ></a>
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
                            <h5><i class="fa fa-home" style="font-size: 30px;margin-right: 30px;"></i>  Carmichael hostel, kolkata-09, West Bengal, India.</h5>
                            <h6><i class="fa fa-envelope" style="font-size: 30px; margin-right: 30px;"></i> kash15if@yahoo.com</h6>
                            <h6><i class="fa fa-external-link" style="font-size: 30px; margin-right: 30px;"></i>https://kashif.fail</h6>
                 
                        </div>
                    <!--info div ends end-->
                    </div>
        
                <!--row ends-->
                </div>

                <button type="button" class="btn btn-primary" v-on:click="showProject">Projects</button>

                <hr>









    <!--container class ends-->
    </div>
</template>

<script>
export default {
  name: 'Portfolio',
  data(){
      return {
          
      };
  },
  methods: {
      showProject: function(){
          this.$emit('showproject');
      }
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
