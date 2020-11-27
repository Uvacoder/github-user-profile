<template>
    <!--whole body container for padding-->
    <div class="container">
        
        <div class="text-center">
            <h3 >Get your own portfolio website</h3>
        </div>
        <br>
        <div class="row">
            <div class="input-group col-md-8 offset-md-2 col-sm-10 offset-sm-1">
                <input type="text" class="form-control" placeholder="Your github username" aria-label="Recipient's username" aria-describedby="basic-addon2" v-model="username">
                <div class="input-group-append">
                  <button class="btn btn-success" type="button" v-on:click="getRepo()">Submit</button>
                </div>
              </div>
        </div>


    <!--container class ends-->
    </div>
</template>

<script>
export default {
  name: 'Input',
  data(){
    return {
      username: ""
    };
  },
  methods:{
    getRepo: function(){
      this.$emit('changerepo',this.username);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container{
            padding-top: 7%;
        }
</style>
