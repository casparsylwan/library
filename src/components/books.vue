<template>
  <div class="books">
      <h1>Hej</h1>
      <div class="container">
        
        <div 
            v-for="info in bookinfo" :key="info.id"
            class="showbooks">
            <router-link :to="setParam(info.id)">    
                <Book v-bind:info="info" ></Book>
            </router-link>
        </div>        
     </div>   
  </div>
</template>


<script>
import Book from './book';
import json from '../assets/data.json';


export default {
  name: 'books',
  components: {
      Book
    
  },
    data(){
        return{
            bookinfo: json.books
              }
          },
          methods:{
              setParam(id){

                  return '/blog/'+id;
              }
          }
  }

</script>
<style scoped lang="scss">

    .container{
        display: grid;
        grid-template-columns: repeat(4, 1fr);
    }

    .showbooks{
        margin: 1rem;
        background-color: #fff;
        
    }

</style>