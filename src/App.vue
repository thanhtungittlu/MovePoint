<template>
  <div id="app">
    <div class="arena">
      <div class="point" ref="point">
      </div>
    </div>
    <div class="dash-board">
      <button @click="clickRight">Right</button>
      <button @click="clickLeft">Left</button>
      <button @click="clickUp">Up</button>
      <button @click="clickDown">Down</button>
      <button @click="clickReset">Reset</button>
    </div>
  </div>
</template>

<script>

export default {
  data: function(){
      return {
        position:{
          x:0,
          y:0,
        },
      }
  },
  methods: {
    clickRight(){
      if (this.position.x == 580 && this.position.y == 580){
        this.position.x = 0
        this.position.y = 0
        
      }else if (this.position.x == 580){
        this.position.x = 0
        this.position.y += 20
      }else{
        this.position.x +=20
      } 
      this.$refs.point.style.marginLeft = this.position.x + "px";
      this.$refs.point.style.marginTop = this.position.y + "px";
    },
    clickLeft(){
      if(this.position.x == 0 && this.position.y == 0){
        this.position.x = 580
        this.position.y = 580
      } else if (this.position.x == 0){
        this.position.x = 580
        this.position.y -= 20
      } else {
        this.position.x -=20
      }
      this.$refs.point.style.marginLeft = this.position.x + "px";
      this.$refs.point.style.marginTop = this.position.y + "px";
    },
    clickUp(){
      if ( this.position.y == 0){
        this.position.y = 580
        
      }else {
        this.position.y -=20
      }
      this.$refs.point.style.marginLeft = this.position.x + "px";
      this.$refs.point.style.marginTop = this.position.y + "px";
    },
    clickDown(){
      if (this.position.y == 580){
        this.position.y = 0
      }else{
        this.position.y +=20
      }
      this.$refs.point.style.marginLeft = this.position.x + "px";
      this.$refs.point.style.marginTop = this.position.y + "px";
    },
    clickReset(){
      this.position.x=0
      this.position.y=0
      this.$refs.point.style.marginLeft = this.position.x + "px";
      this.$refs.point.style.marginTop = this.position.y + "px";
    },
  },

}
</script>

<style>
  .arena {
    margin-left: 50px;
    margin-top: 50px;
    width: 600px;
    height: 600px;
    border: 1px solid black;
    
  }
  .point{
    width: 20px;
    height: 20px;
    background-color: red;
    border-radius:50%;
    margin-left:0px;
    margin-top:0px;
    
  }
  .dash-board{
    margin-top: 50px;
    margin-left: 200px;
  }
</style>
