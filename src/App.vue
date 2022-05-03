<template>

  <div class="black-bg" v-if="modalState == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="modalState=false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(menu, i) in menues" :key="i">{{menu}}</a>

  </div>

  <!-- <div v-for="(product,i) in products" :key="i">
    <h4>{{product}}</h4>
    <p>xx 만원</p>
    <button @click="increase(i)">허위매물신고</button>
    <span>신고수 : {{reports[i]}}</span>
  </div> -->
  <div>
    <img src="./assets/room0.jpg" class="room-img">
    <h4 @click="modalState=true">{{products[0]}}</h4>
    <p>50 만원</p>
    <button @click="increase(0)">허위매물신고</button> <span>신고수 : {{reports[0]}}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4 :style="h4style">{{products[1]}}</h4>
    <p>{{price1}} 만원</p>
    <button @click="increase(1)">허위매물신고</button> <span>신고수 : {{reports[1]}}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4>{{products[2]}}</h4>
    <p>{{price2}} 만원</p>
    <button @click="increase(2)">허위매물신고</button> <span>신고수 : {{reports[2]}}</span>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {

      modalState : false,


      reports : [0,0,0],

      menues : ['Home', 'Shop', 'About'],

      price1 : 60,
      price2 : 70,
      h4style : "color : blue",
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods : {
    increase(i){
      this.reports[i]++;
    }
  },

  components: {
  }
}
</script>

<style>

body{
  margin: 0;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;  
}
.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}


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

.room-img{
  width:100%;
  margin-top: 40px;
}

</style>
