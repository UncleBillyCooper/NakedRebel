<template>
 <div class="podium">
  <div class="top">
   <rebel_hat id="hat"/>
   <rebel_jacket id="jacket" 
   :style="{ background: `url(${jacketColor.currentColor})` }"
   @click="setJacketColor()"/>
   
   <rebel_trousers id="trousers" 
   :style="{ background: `url(${trousersColor.currentColor})` }"
   @click="setTrousersColor()"/>
  </div>

  <div class="information">
   <h4><b :style="{color: textColorJacket}">Jacket:</b> {{ jacketColor.currentNameColor }}</h4>
   <h4><b :style="{color: textColorTrousers}">Trousers:</b> {{ trousersColor.currentNameColor }}</h4>
   <h4><b :style="{color: textColor}">Selected color:</b> {{ currentObject.currentNameColor }}</h4>
  </div>
  <!--<img src="../assets/Sanya.png" alt="">-->
  
  <!-- <div class="circle" :style="{ background: 'url('+activeBackGround+')' }"></div> -->
 </div>
</template>

<script>
 import rebel_jacket from "../components/rebelJacket.vue";
 import rebel_hat from "../components/rebelHat.vue";
 import rebel_trousers from "../components/rebelTrousers.vue";

 export default {
  
  props: {
   currentObject: {
    type: Object
   }
  },
  
  data() {
   return {
    
    textColorJacket: 'black',
    textColorTrousers: 'black',
    textColor: 'red',
    jacketColor: {},
    trousersColor: {},

    
    
   }
  },
  

  methods: {
    setJacketColor() {
      this.jacketColor=JSON.parse(JSON.stringify(this.currentObject))
      this.textColorJacket='green'
      this.textColorTrousers='black'
    },

    setTrousersColor() {
      this.trousersColor=JSON.parse(JSON.stringify(this.currentObject))
      this.textColorJacket='black'
      this.textColorTrousers='green'
    }
    
   },
 
  components: {
   rebel_jacket,
   rebel_hat,
   rebel_trousers,
  }
 }
</script>

<style scoped>
.podium {
 display: flex;
 flex-direction: column;
 justify-content: space-between;
 padding: 5px;
 width: 25%;
 min-width: 200px;
 height: 100%;
 /*border: 2px black solid;*/
 border-left: 6px solid gray;
 background-color: rgb(192,192,192);
 border-radius: 10px;
 box-shadow: -4px 0px 4px 0px rgba(128, 128, 128, 0.8);
 
 /*transform: rotate3d(0,1,0,40deg)*/
}


.top{
 /*border: 2px black solid;*/
 height: 84%;
 position: relative;
}

#hat{
 position: absolute;
 left: 28%;
 top: 3vh;
}

#jacket{
 position: absolute;
 left: 15%;
 /*top: 15%;*/
 top: 10vh;
 z-index: 2;
}

#trousers{
 position: absolute;
 left: 32%;
 top: 30vh;
 z-index: 1;
}

.information{
 /*border: 2px black solid;*/
 height: 15%;
}
/*.circle {
 width: 100px;
 height: 100px;
 border: 2px black solid;
 border-radius: 50%;
}

img {
 width: 100%;
 height: 100%;
 object-fit: cover;
}*/
</style>
