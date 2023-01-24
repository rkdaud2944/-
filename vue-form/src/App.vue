<template>

  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <h4>{{data[push].title}}</h4>
      <p>{{data[push].content}}</p>
      <button @click="modal = false"> 닫기 </button>
    </div>

  </div>



  <p class="title">코끼리 커뮤니케이션</p>
    <div class="menu">
        <a v-for="a in menus" :key="a"> {{ a }}</a>
    </div>

      <div v-for="(b,i) in data" :key="i">
        <img :src="b.img" class="contents-img" @click="modal = true ; push = i ">
        <h4> {{b.title}} </h4>
        <p>{{b.price}}만원</p>
        <button @click="recommend[i]++">추천버튼</button>
        <span>추천수 : {{recommend[i]}}</span>
      </div>

</template>

<script>

import data1 from './assets/data.js';

export default {
  name: 'App',
  data(){
    return {
      push : 0,
      data : data1,
      modal :  false,
      price : ['10','1','100'],
      recommend : ['0','0','0'],
      menus : ['코끼리 상품', '진짜 코끼리', 'QnA'],
      products : ['코끼리 봇','코끼리 용품','아프리카 코끼리']
    }
  }, 
  
  methods : {
    report(){
      this.Howmuchreport[1] ++ ;
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
  margin-top: 30px;
}

.menu {
  background: grey;
  padding:  15px;
  border-radius: 5px;
  margin-top: 60px;
}

.menu a {
  color: white;
  padding: 100px;
}

.title {
  font-size: 30px;
  font-family: 'Courier New', Courier, monospace;
}

.contents-img {
  width: 30%;
  margin-top: 40px;
}

body {
  margin : 0
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 5px;
  padding: 20px;
}
</style>
