<template>
  <div id="app">
  
    <Card v-bind:product="product" @change-img="changeImg"/>
  </div>
</template>

<script>
import Card from "./components/Card";




export default {
  name: "App",
  data(){
    return {

    }
  },
  components: {
    Card
  },
  methods:{
    changeImg(path){
      this.product.mainImg = path;
    }
  }
};
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  max-width: 100vw;
  min-height: 100vh;
  background: #E5E5E5;
}
</style>
