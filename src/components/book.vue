<template>
  <div class="book">
    <div 
        class="cover" 
        :class="setColorClass(info.id)"
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
      },

      setColorClass(id){
          if(id===1){
            return "yellow"  
          }else if(id===2){
              return "l-blue"
          }else if(id===3){
              return "green"
          }else if(id===4){
              return "brown"
          }else if(id===5){
              return "red"
          }else if(id===6){
              return "d-blue"
          }else if(id===7){
              return "purple"
          }else if(id===8){
              return "l-blue"
          }
          
      }
  }

}
</script>
<style scoped lang="scss">

     $yellow:    linear-gradient(to right top, rgba(50,50,50,1), rgba(50,50,50,0.3), rgba(100,100,100,0.3),rgba(150,150,150,0.3), rgba(255,255,255,0.3));
    // $l-blue:    linear-gradient(to right top, #00bbbb, #00cccc, #00dddd, #00eeee, #00ffff);
    // $green:     linear-gradient(to right top, #228855, #33a469, #43c27e, #54e094, #66ffaa);
    // $brown:     linear-gradient(to right top, #aa7711, #bf8324, #d49035, #e99d45, #ffaa55);
    // $d-blue:    linear-gradient(to right top, #003388, #004fa7, #006dc5, #008be3, #00aaff);
    // $red:       linear-gradient(to right top, #882200, #a42500, #c12600, #e02500, #ff2200);
    // $purple:    linear-gradient(to right top, #540054, #6c006c, #750075, #8f008f, #aa00aa);

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

        // &.yellow{
        //     background-image: $yellow;
        // }

        // &.l-blue{
        //     background-image: $l-blue;
        // }
        // &.green{
        //     background-image: $green;
        // }
        // &.brown{
        //     background-image: $brown;
        // }
        // &.d-blue{
        //     background-image: $d-blue;
        // }

        

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