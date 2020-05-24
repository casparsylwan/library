<template>
  <div class="blog">
    <div class="box">
      <div class="top">
        <router-link to="/about">
          <div class="arrow-back">
            <p>
              &#8592; 
            </p>
          </div>
        </router-link>
        </div>
      <div class="left">
      
      <Book class="book" v-bind:info="info" ></Book>
      </div>
      <div class="rigth">
        <h1>{{ info.title }}</h1>
        <p> by {{ info.author }} </p>
        <section>
          <p>
          {{ info.plot }}
          </p>

          <div class="info">
            <p> pages: {{ info.pages }}  </p>
            <p> audience: {{ info.audience }} </p>
            <p> publisher: {{ info.publisher }} </p>
            <p> year: {{ info.year }} </p>
          </div>
          <div class="btn">
            <p>Oh, I want to read it!</p>            
          </div>
        </section>
      </div>
    </div>
    <!--
    {{ $route.params.id }}
    -->
  </div>
</template>

<script>
import Book from '../components/book';
import json from '../assets/data.json';


export default {
  name: 'blog',
  components: {
    Book   
  },
  props:[],
    data(){
        return{
          //  info: json.books[this.$route.params.id-1],
            info: json.books[json.books.findIndex(x => x.id == this.$route.params.id)] ,
            bookInfo:json.books
            
              }
          },
           methods:{
              setParam(){

                  let index = this.bookInfo.findIndex(x => x.id == this.$route.params.id);
                   
                  return index;
              }
          }

}
</script>
<style scoped lang="scss">

  .blog{
    max-width: 60rem;
    min-height: 100Vh;
    margin: 0 auto;
    background-color: #000;
  }

  .box{
    padding: 2rem;
    background-color: #000;
    display: grid;
    grid-template-areas: 
    "top top top top"
    "book book text text";
   
    color: #fff;

    .top{
      grid-area: top;
      width: 100;
    }

    .arrow-back{
      
      height: 2.5rem;
      width: 2.5rem;
      border-radius: 100%;
      background-color: #777;
      color: #000;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.5rem;
      font-weight: bold;
      margin-bottom: 2rem;
      

        p{
          margin-top: -.25rem;
        }

       
    }

    .book{
      grid-area: book;
    }

    

    .rigth{
      grid-area: text;
      margin-left: 2rem;

      h1{
        font-weight: bolder;
        font-size: 2rem;
        margin-bottom: 0.5rem;
      }

     
      

      section{ 
        
        margin-top: 1rem;

        p{
        letter-spacing: 1px;
        line-height: 1.5rem;
        
        }
      }

      .info{
        background-color: lighten($color: #000000, $amount: 10%);
        margin: 1rem 0 1rem 0;
        padding: 1rem;
        display: grid;
        grid-template-columns: repeat(2,1fr);
      }

      .btn{
       
        width: 40%;
        border-radius: 10px;
        background-color: #fff;
        color:#000;
        padding: 2%;
        text-align: center;

        p{
          font-size: 1.2rem;
          font-weight: bold;
        }
          
      }

    }

  }

  

</style>