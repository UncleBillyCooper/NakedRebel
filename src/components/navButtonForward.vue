<script>
export default {

}
</script>

<template>
<button><slot></slot></button>
</template>

<style scoped>
button{
  width: 30%;
  height: 100%;
  clip-path: polygon(75% 0%, 90% 50%, 75% 100%, 0% 100%, 10% 50%, 0% 0%);
  font-size: calc(2 * (1vw + 1vh));
  
  background-color: rgb(0, 255, 0);
  border: none;
  border-bottom: 6px rgb(0,100,0) solid;
}

button:active {
  animation-name: anim;
  animation-duration: 0.3s;
  
}

@keyframes anim {
  0% {
    border-bottom: 6px rgb(0,100,0) solid;
  }

  100% {
    border-bottom: 0px rgb(0,100,0) solid;
  }

  
}
</style>
