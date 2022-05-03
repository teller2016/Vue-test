<template>

  <div class="menu">
    <a v-for="(menu, i) in menues" :key="i">{{menu}}</a>

  </div>

  <div v-for="(product,i) in products" :key="i">
    <h4>{{product}}</h4>
    <p>xx 만원</p>
  </div>
  <!-- <div>
    <h4>{{products[0]}}</h4>
    <p>50 만원</p>
  </div>
  <div>
    <h4 :style="h4style">{{products[1]}}</h4>
    <p>{{price1}} 만원</p>
  </div>
  <div>
    <h4>{{products[2]}}</h4>
    <p>{{price2}} 만원</p>
  </div> -->
</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      menues : ['Home', 'Shop', 'About'],

      price1 : 60,
      price2 : 70,
      h4style : "color : blue",
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

</style>
