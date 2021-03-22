<template>
  <div class="hello">
    <div :key="index" v-for="(makeup, index) in makeup ">
       <h1> {{makeup.name}} </h1>
       <img :src=" makeup.picture" alt="">
    </div>
   
  </div>  
</template>

<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  data(){
    return{
      makeup: null,
    }
  },
  mounted(){
    axios
    .get('http://makeup-api.herokuapp.com/api/v1/products.json')
    .then((reponse) => {
      this.makeup = reponse.data;
      console.log(this.makeup)
    });
},
 
}
</script>


<style scoped>

</style>
