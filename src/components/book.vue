<template>
  <div class="book">
    <div 
        class="cover" 
        
        :style='setGradientColor(info.color)'>
        <div class="border">
            <section class="title">
                <h2>{{ info.title }}</h2>
                <h3>{{ info.author }}</h3>  
            </section>            
        </div>        
    </div>
  </div>
</template>

<script>
export default {
  name: 'blog',
  components: {
    
  },
  props:["info"],
  methods :{

      setGradientColor(color){
          return { backgroundColor: color }
      }
  }

}
</script>
<style scoped lang="scss">

     $yellow:    linear-gradient(to right top, rgba(100,100,100,0.6), rgba(100,100,100,0.5), rgba(100,100,100,0.3),rgba(150,150,150,0.4), rgba(255,255,255,0.5));

    .book{
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .cover{
        position: relative;
        height: 25rem;
        width: 20rem;
        background-image: $yellow;

        .border{
            position: absolute;
            top:0;
            bottom: 0;
            left:1.5rem;
            right: 1rem;
            border-left: 3px solid rgba(50,50,50,0.5);

            display: flex;
            flex-direction: column;
            align-items: flex-start;
            justify-content: flex-end;

            section{
            
            margin-left: 2rem;
            margin-bottom: 10%;
        }

        }

        
        
    }

    section{
        display: flex;
        flex-direction: column ;        
        color: #fff;

        h2{
            font-size: 2rem;
            font-weight: bolder;    
        }

        h3{
            font-size: 1.5rem;
            font-weight: 500;
        }

    }

    

    



</style>