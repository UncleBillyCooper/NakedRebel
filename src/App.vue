<template>
  <Transition name="exit__main-container">
    <div class="main-container" v-if="visIntro===true">
      <MainTittle/>
      <mainButton @:click="exitIntro"/>
    </div>
  </Transition>>
    <div class="action-container" v-if="visIntro===false">
      <!--<gridSlider :ItemList="lists"/>-->
      <gridSlider :ItemList="lists" @sendcard="setCurrentCard"/>
      <!-- <gridSlider :ItemList="lists"/> -->
      <showRoom class="show-room" :currentObject="currentData"/>
       
      
      
    </div>
    
</template>

<script>
import mainButton from "./components/mainButton.vue";
import MainTittle from "./components/MainTittle.vue";
import showRoom from "./components/showRoom.vue";
import gridSlider from "./components/gridSlider.vue";




export default {
  data() {
    return {
      visIntro: true,
      lists: [{id: 1, name: 'Drab Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/jean/thumbnails/drab_thumbnail.gif'}, {id: 2, name: 'Light Gray Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/jean/thumbnails/natural-light-gray_thumbnail.gif'},
               {id: 3, name: 'Natural Cream Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/jean/thumbnails/natural-cream-jean_thumbnail.gif'}, {id: 4, name: 'Logwood Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/thumbnails/logwood-jean_thumbnail.gif'},
               {id: 5, name: 'Sumac Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/thumbnails/sumacjean_thumbnail.jpg'}, {id: 6, name: 'Sampson Gray Jean', image: 'https://www.tartextextiles.com/assets/images/thumbnails/Sampson gray_thumbnail.jpg'},
               {id: 7, name: 'Sumac Mix Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/thumbnails/sumac-mix_thumbnail.gif'}, {id: 8, name: 'Cadet Jean', image: 'https://www.tartextextiles.com/assets/images/thumbnails/cadet_thumbnail.jpg'},
               {id: 9, name: 'Blue Gray Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/jean/thumbnails/blue-gray-jean_thumbnail.gif'}, {id: 10, name: 'Butternut Rust Jean', image: 'https://www.tartextextiles.com/assets/images/thumbnails/butternut rust_thumbnail.jpg'},
               {id: 11, name: 'Ash Jean', image: 'https://www.tartextextiles.com/assets/images/thumbnails/ash-jean_thumbnail.jpg'}, {id: 12, name: 'Natural Slub all Cotton  Jean', image: 'https://www.tartextextiles.com/assets/images/thumbnails/cottonSlub_thumbnail.jpg'},
               {id: 13, name: 'Coarse Weave Logwood Jean', image: 'https://www.tartextextiles.com/assets/images/thumbnails/Coarse-logwood_thumbnail.jpg'}, {id: 14, name: 'Natural all Cotton  Jean', image: 'https://www.tartextextiles.com/assets/images/thumbnails/NatCottonJN_thumbnail.jpg'},
               {id: 15, name: 'Dark Charcoal Gray Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/thumbnails/dark charcoal gray_thumbnail.jpg'}, {id: 16, name: 'Brown all Cotton  Jean', image: 'https://www.tartextextiles.com/assets/images/thumbnails/BrownCTNJean_thumbnail.jpg'},
               {id: 17, name: 'Little Rock Frock Coat Fabric', image: 'https://www.tartextextiles.com/assets/images/thumbnails/little rock_thumbnail.jpg'}, {id: 18, name: 'Blue all Cotton  Jean', image: 'https://www.tartextextiles.com/assets/images/thumbnails/BlueCottonJean_thumbnail.jpg'},
               {id: 19, name: 'Richmond Gray Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/thumbnails/Richmond gray_thumbnail.jpg'}, {id: 20, name: 'Gray Mix Jean', image: 'https://www.tartextextiles.com/assets/images/thumbnails/FineGrayMx_thumbnail.jpg'},
               {id: 21, name: 'Gray Mix  on black Jean', image: 'https://www.tartextextiles.com/assets/images/thumbnails/FineGrayMixonBlack_thumbnail.jpg'}, {id: 22, name: 'Blue and White Variegated Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/thumbnails/blueWhiteVar_thumbnail.jpg'},
               {id: 23, name: 'Chestnut Jean', image: 'https://www.tartextextiles.com/assets/images/thumbnails/Chestnut_thumbnail.jpg'}, {id: 24, name: 'Royal Blue Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/thumbnails/royalblue622_thumbnail.jpg'},
               {id: 25, name: 'Dark Gray Jean', image: 'https://www.tartextextiles.com/assets/images/thumbnails/Dark Gray Jean_thumbnail.jpg'}, {id: 26, name: 'Royal Blue wool blend Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/thumbnails/WN Royal Blue Jean_thumbnail.jpg'},
               {id: 27, name: 'blue and white variegated jean cloth', image: 'https://www.tartextextiles.com/assets/images/thumbnails/bluewhitevariegated_thumbnail.jpg'}, {id: 28, name: 'Brown and white variegated Jean Cloth ', image: 'https://www.tartextextiles.com/assets/images/thumbnails/BrownWhiteVarigated412_thumbnail.jpg'},
               {id: 29, name: 'Black Woolen Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/thumbnails/Black Jean522_thumbnail.jpg'}, 
               {id: 30, name: 'Black and white variegated Jean Cloth', image: 'https://www.tartextextiles.com/assets/images/thumbnails/BlkWhtVar_thumbnail.jpg'}
              ],
      currentData: {
        currentColor: '',
        currentNameColor: '',
      }
              
    }

  },

  methods: {
    exitIntro() {
      this.visIntro=false
    },

    setCurrentCard (el) {
      this.currentData.currentColor=el.image,
      this.currentData.currentNameColor=el.name
      console.log(this.currentData)  
      //console.log(el)
    }
  },

  components: {
    mainButton,
    MainTittle,
    showRoom,
    
    gridSlider
   }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
  width: 100vw;
  height: 100vh;
}

#app {
  width: 100%;
  height: 100%;
  background: url('./assets/main_background.jpg') 0 0/cover no-repeat;
}

.main-container{
  display: flex;
  /*display: none;*/
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  width: 100%;
  height: 98%;
  background: linear-gradient(180deg, rgba(255,255,255,0.8) 45%, rgba(255,255,255,0) 100%);
  perspective: 400px;
  perspective-origin: center;
}

.exit__main-container-leave-active {
  transition: opacity 2s ease;
}

.exit__main-container-leave-to {
  opacity: 0;
}

.action-container{
  display: flex;
  /*display: none;*/
  justify-content: space-between;
  width: 100vw;
  height: 97vh;
  /*border: 2px black solid;*/
  padding: 0px 20px 10px 20px;
  perspective: 400px;
  perspective-origin: center;
}

.show-room{
  animation-name: animPodium;
  animation-duration: 1s;
}

@keyframes animPodium {
  0% {
    transform: rotate3d(0,1,0,40deg)
  }

  100% {
    transform: rotate3d(0,1,0,0deg)
  }
}

</style>
