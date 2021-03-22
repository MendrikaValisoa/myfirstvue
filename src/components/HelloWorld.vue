<template>
<table>
  <div class="hello">
    <div :key="index" v-for="(makeup, index) in makeup ">
      <tr>
        <td>
       <h1> {{makeup.name}} </h1>
       </td>
       <td>   
       <img :src="makeup.image_link" alt="" style="width:20%">
       </td>
       <td>  
       <h1> {{makeup.category}} </h1>
       </td>
       </tr>
    </div>
  </div>
  </table>  
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
