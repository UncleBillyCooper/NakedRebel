<script>
import navButtonForward from "./navButtonForward.vue";
import navButtonBackward from "./navButtonBackward.vue";
 export default{
  props: {
    ItemList: {
      type: Array
    }
  },

  components: {
    navButtonForward,
    navButtonBackward,
  },
  
  data() {
    return {
      visible: 3,
      
    }
  },

  methods: {
    btnForward() {
        if (this.visible == 1) {
          this.visible=2;
        } else if (this.visible == 2) {
          this.visible = 3;
        } else {
          this.visible=1
        }
    },
    btnBackward() {
      if (this.visible == 3) {
          this.visible=2;
        } else if (this.visible == 2) {
          this.visible = 1;
        } else {
          this.visible=3
        }
    },
    sendData(el) {
      this.$emit('sendcard', el)
    }
  }
 }
</script>

<template>
 <div class="grid-container">
  <div class="items slide1" v-if="visible===1">
    <div class="card" :id="card.id" v-for="(card,index) in ItemList.slice(0, 10)" :key="index" @click="sendData(card)">
          <img :src="card.image" alt="Какая-то картинка" />
          <h2 class="title">{{ card.name }}</h2>
    </div>
  </div>
  <div class="items slide2" v-if="visible===2">
    <div class="card" :id="card.id" v-for="(card,index) in ItemList.slice(10, 20)" :key="index" @click="sendData(card)">
          <img :src="card.image" alt="Какая-то картинка" />
          <h2 class="title">{{ card.name }}</h2>
    </div>
  </div>
  <div class="items slide3" v-if="visible===3">
    <div class="card" :id="card.id" v-for="(card,index) in ItemList.slice(20, 30)" :key="index" @click="sendData(card)">
          <img :src="card.image" alt="Какая-то картинка" />
          <h2 class="title">{{ card.name }}</h2>
    </div>
  </div>  
   <nav class="buttons">
   
   <navButtonBackward class="btn-back" @click="btnBackward">Назад</navButtonBackward>
   <div class="currentSlideNum">
    <img src="../assets/m_frame.png" alt="Какая-то картинка" class="back">
    <h2>{{ visible }}</h2>
    <img src="../assets/frame.png" alt="Какая-то картинка" class="forward">
   </div>
   <navButtonForward class="btn-forward" @click="btnForward">Вперед</navButtonForward>
   
  </nav>
  
</div>

</template>

<style scoped>
 @font-face {
 font-family: Carnaval;
 src: url(../fonts/Carnevalee\ Freakshow.ttf);
}
 
@font-face {
 font-family: myKellySlab;
 src: url(../fonts/kelly-slab_[allfont.ru].ttf);
}
 
 .grid-container{
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 70%;
  height: 100%;
  /*border: 2px black solid;*/
  border-radius: 10px;
  padding: 10px;
 }

 .items {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: repeat(5, 1fr);
  row-gap: 10px;
  column-gap: 10px;
  width: 100%;
  height: 85%;
  /*border: 2px black solid;*/
 }

  

 .card{
  width: 80%;
  height: calc(4.5vw + 4.5vh);
  border-bottom: 4px grey solid;
  border-right: 4px grey solid;;
  padding: 5px;
  margin: 0 auto;
  border-radius: 20px;
  display: flex;
  justify-content: space-between;
  background-color: black;
  box-shadow: 9px 9px 4px 0px rgba(34, 60, 80, 1);
  /*animation-name: rotate;
  animation-duration: 0.2s;
  animation-iteration-count: 5;
  animation-delay: 0.1s;*/
 }

/*.card:hover {
  animation-name: rotate;
  animation-duration: .1s;
  animation-iteration-count: 5;
  animation-delay: 0.3s;
}*/

@keyframes rotate {
  0% {
    transform: rotateX(0deg);
  }

  100% {
    transform: rotateX(180deg);
  }
}

 .card>img {
  width: 15%;
  height: 100%;
  border-radius: 50%;
 }
.title {
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  width: 80%;
  height: 100%;
  /*border: 2px black solid;*/
  letter-spacing: 1px;
  font-weight: 300;
  color: white;
  font-family: 'Carnaval';
  font-size: calc(1.5vw + 1.5vh);
}
 
 .item{
  border: 2px black solid;
 }

 nav{
   display: flex;
   
   justify-content: center;
   margin-top: 10px;
   width: 100%;
   height: 12%;
   /*border: 2px black solid;*/
   align-self: center;
   padding: 10px 0px 10px 0px;
 }

 .btn-back, .btn-forward {
  font-family: 'myKellySlab';
  font-weight: 600;
 }

 .currentSlideNum{
  display: flex;
  justify-content: center;
  width: 30%;
 }

 .currentSlideNum>img {
  width: 30%;
  height: 100%;
  color: black;
 }

 
.currentSlideNum>h2{
  font-size: calc(3vw + 3vh);
  
}



/*button {
  width: 30%;
  height: 100%;
  font-size: calc((1vw+1vh)*2);
  border-radius: 10px;
  background-color: green;
  box-shadow: 18px 18px 0px 2px rgba(34, 60, 80, 0.35);
}

 .forward:hover {
  background-color: red;
 }*/

 @media (max-width: 860px) {
    .items{
      grid-template-columns: repeat(1, 1fr);
      overflow-y: scroll;
      overflow-x: hidden;
    }

    .card{
      height: calc(8vw + 8vh);
    }
    .title {
      font-size: calc(2vw + 2vh);
  
    }

    .back{
      display: none;
    }

    .forward{
      display: none;
    }

    .currentSlideNum>h2{
      font-size: calc(4vw + 4vh);
  
    }
  }

  @media (max-width: 450px) {
    .title {
      display: none;
    }

    .card>img {
      width: 100%;
      object-fit: cover;
      margin: 0;
      border: none;
      border-radius: 0%;
    }

    .card{
      /*width: 22%;
      margin: 0 auto;*/
      padding: 0;
      border-radius: 0%;
      border: none;
    }
    .currentSlideNum>h2{
      font-size: calc(5vw + 5vh);
  
    }
  }
</style>
