<script>
 export default {
  data() {
   return {
    visButton: true,
    animButton: 'none',
   }
  },
  methods: {
   exitButton() {
    
    this.visButton=false
   }
  }
 }
</script>

<template>
  
 
 <Transition name="buttonOut">
  <div class="button" v-if="visButton===true">
   <button @:click="visButton=false">CHARGE!!!</button>
  </div>
 </Transition>
 
 
 
</template>

<style scoped>
 

@font-face {
 font-family: myPlaybill;
 src: url(../fonts/playbillbtcyr.ttf);
}
.button{
 width: 50vw;
 height: 8vw;
 /*border: 2px black solid;*/
 border: none;
 
 display: flex;
 justify-content: center;
 align-items: center;
 
}
 button{
  width: 50vw;
  height: 8vw;
  border-radius: 10px;
  background: linear-gradient(135deg, rgba(49,38,177,0.65) 0%, rgba(255,0,10,0.87) 60%, rgba(36,43,220,0.61) 100%);
  font-family: 'myPlaybill';
  font-size: calc(.7 * (1vw + 1vh));
  border-bottom: 6px rgba(139, 0, 0,1) solid;
  border-left: 6px rgba(139, 0, 0,.8) solid;
  letter-spacing: 1px;
  color: black;
  -webkit-box-shadow: -13px 13px 15px 5px rgba(30, 30, 11, 1);
  -moz-box-shadow: -13px 13px 15px 5px rgba(30, 30, 11, 1);
  box-shadow: -13px 13px 15px 5px rgba(30, 30, 11, 1);
  
 }

 .buttonOut-leave-active {
  animation: exit 1s;
 }

 @keyframes exit {
  0% {
   transform: rotateX(0deg) scale(1, 1);
  }

  10% {
   transform: rotateX(45deg) scale(1, 1);
  }

  20% {
   transform: rotateX(80deg) scale(0.8, 0.8);
  }

  30% {
   transform: rotateX(90deg) scale(0.5, 0.5);
  }

  90% {
   transform: rotateX(120deg) scale(0.3, 0.3);
  }

  100% {
   transform: rotateX(180deg) scale(0, 0);
  }
 }
</style>
