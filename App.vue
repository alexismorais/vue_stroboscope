<template>
  <div :style="{backgroundColor:bgColor}">
    hello  
    <button @click="stopstart()">Btn</button>
  </div>

</template>

<script>


function Random(max){
  return Math.floor(Math.random() * Math.floor(max));
}

export default {
  data(){

    return{
      bgColor:'white',
      couleur:['red','blue','yellow','pink'],
      timer:null,
    }
  },
  methods: {
      stopstart(){
        if(this.timer){
          clearInterval(this.timer);
          this.timer=null;
          return;
        }
        this.timer = setInterval(this.changeColor,25);
      },

      changeColor(){
         this.bgColor = this.couleur[Random(4)];
      }
    
  }
}


</script>

<style>
  div{
    position:fixed;
    top:0;
    bottom:0;
    right:0; 
    left:0;
  }
</style>

