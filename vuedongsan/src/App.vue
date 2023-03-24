<template>

  <!--모달-->
  <div class="black-bg" v-if=" 모달창상태 == false">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button type="button" @click=" 모달창상태 = true">닫기</button>
    </div>
  </div>
  <!--/모달-->

  <!--메뉴-->
  <div class="menu">
    <a href="javascript:void(0)" v-for="(menuList,i) in menus" :key="i">{{ menuList }}</a>
  </div>
  <!--//메뉴-->
  <!--원룸 가격 리스트-->
  <div v-for="(a,i) in products" :key="a">
    <img :src="require('./assets/room' + i + '.jpg')"  class="room-img">
    <h4 @click=" 모달창상태 = false ">{{ products[i] }} 원룸</h4>
    <p>{{ price[i] }} 만원</p>
    <button @click="increase(i)">허위매물신고</button> <span>신고수 : {{ 신고수[i] }}</span>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      모달창상태 : true,
      신고수 : [0,0,0],
      price : [60,100, 130],
      products: ['역삼동원룸','천호동원룸','마포구원룸'],
      menus : ['Home','Procuts','About'],
    }
  },
  methods: {
    increase(e) {
      this.신고수[e] += 1;
    }
  },
}
</script>

<style>

body {margin:0;}

div {box-sizing: border-box;}

.black-bg {width:100%; height:100%; background: rgba(0,0,0,0.5); position:fixed; padding:20px;}

.white-bg {width:100%; background:#FFFFFF; border-radius:8px; padding:20px;}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding:15px;
  border-radius: 5px;
}
.menu a {
  color: #FFFFFF;
  padding: 10px;
}
.room-img {width:100%; margin-top: 40px;}

</style>
