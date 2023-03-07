<template>
  <!--메뉴-->
  <div class="menu">
    <a href="javascript:void(0)" v-for="(menuList,i) in menus" :key="i">{{ menuList }}</a>
  </div>
  <!--//메뉴-->
  <!--원룸 가격 리스트-->
  <div v-for="(a,i) in products" :key="a">
    <h4>{{ products[i] }} 원룸</h4>
    <p>{{ price[i] }} 만원</p>
    <button @click="this.신고수 += 1">허위매물신고</button> <span>신고수 : {{ 신고수 }}</span>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      신고수 : 0,
      price : [60,100, 130],
      products: ['역삼동원룸','천호동원룸','마포구원룸'],
      menus : ['Home','Procuts','About'],
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

.menu {
  background: darkslateblue;
  padding:15px;
  border-radius: 5px;
}
.menu a {
  color: #FFFFFF;
  padding: 10px;
}
</style>
