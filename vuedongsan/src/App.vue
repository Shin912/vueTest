<template>

  <div class="black-bg" v-if="모달창오픈 == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p v-for="(a,i) in 원룸들" :key="i">
        {{ a.content }}
      </p>
      <button @click="모달창오픈 = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
    <!-- -->
  </div>
    
  <div v-for="(a,i) in 원룸들" :key="i">
    <!-- 반복문 -->
    <img :src="a.image" class="room-img">
    <h4 @click="모달창오픈 = true">{{ a.title }}</h4>
    <p>{{a.price}} 원</p>
  </div>

  <div>
    <img :src="원룸들[0].image" class="room-img">
    <h4>{{ 원룸들[0].title }}</h4>
    <p>{{원룸들[0].price}} 원</p>
  </div>
  <div>
    <img :src="원룸들[1].image" class="room-img">
    <h4>{{ 원룸들[1].title }}</h4>
    <p>{{원룸들[1].price}} 원</p>
  </div>
  

 
      <!-- <div v-for="(a,i) in products" :key="i"> 반복문 예시
        <h4 >{{ a }}</h4>
        <p >50 만원</p>
        <button @click="신고수++">허위매물신고</button> <span>신고수 : {{ 신고수 }}</span>
      </div> -->

      <div>
        <img src="./assets/room0.jpg" class="room-img">
        <h4 @click="모달창오픈 = true">{{ products[0] }}</h4>
        <p >{{ price[0] }} 만원</p>
        <button @click="신고수[0]++">허위매물신고</button> <span>신고수 : {{ 신고수[0] }}</span>
      </div>
      <div>
        <img src="./assets/room1.jpg" class="room-img">
        <h4 @click="모달창오픈 = true">{{ products[1] }}</h4>
        <p >{{ price[1] }} 만원</p>
        <button @click="신고수[1]++">허위매물신고</button> <span>신고수 : {{ 신고수[1] }}</span>
      </div>
      <div>
        <img src="./assets/room2.jpg" class="room-img">
        <h4 @click="모달창오픈 = true">{{ products[2] }}</h4>
        <p >{{ price[2] }} 만원</p>
        <button @click="신고수[2]++">허위매물신고</button> <span>신고수 : {{ 신고수[2] }}</span>
      </div>
</template>

<script>

import data from './assets/oneroom.js';

export default {
  name: 'App',
  data(){
    return{
      원룸들 : data,
      모달창오픈: false,
      신고수 : [0,0,0],
      메뉴들 : [ 'Home', 'Shop', 'About'],
      스타일 : 'color : red',
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      price : [ '80', '70', '60'],
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
  margin-top: 60px;
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
  width: 100%;
  margin-top: 40px;
}
body{
  margin: 0;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
