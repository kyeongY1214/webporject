<template>
  <div class="app">
    <div class="container">
      <div class="content row brand">
        <div class="col-md-6">
          <img class="pb-4" src="img/main.jpg" />
        </div>
        <div class="col-md-6" style="margin-top:100px;">
          <h2 class="h2-seo" style="color: black">I will live alone</h2>
          <div style="color: black; text-size: 16px">
            혼족, 일코노미, 나홀로족...
          </div>
          <h5 class="h2-seo" style="color: black">이제는 1인 가구 시대!</h5>
          <div class="text-center">
            <router-link to="/search"
              ><a class="btn btn-primary btn-lg btn-block"
              style="border-radius: 10px;"
                >검색하기</a
              ></router-link
            >
            <router-link to="/qna"
              ><a class="btn btn-warning btn-lg btn-block"
               style="border-radius: 10px;"
                >추천하기</a
              ></router-link
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { mapActions } from "vuex";

export default {
  name: "start",
  bodyClass: "start-page",
  methods: {
    ...mapActions("question", ["requestQuestion"]),
    getQuestionList() {
      this.requestQuestion();
      
    },
    
  },
  created(){
    this.requestRoomType();
    this.requestBargainType();

  },
  methods:{
    ...mapActions('search', ['requestRoomType', 'requestBargainType']),
  },
};
</script>
<style>
.app {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}

.button {
  position: relative;
  z-index: 2;
  background-color: #fff;
  border: 2px solid #333;
  color: #333;
  line-height: 50px;
  overflow: hidden;
  border-radius: 30px;

  display: inline-block;
  width: 200px;
  height: 45px;
  text-align: center;
  text-decoration: none;
  line-height: 45px;
  outline: none;
}
.button::before,
.button::after {
  position: absolute;
  z-index: -1;
  display: block;
  content: "";
}
.button,
.button::before,
.button::after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
  -webkit-transition: all 0.3s;
  transition: all 0.3s;

  top: -100%;
  width: 100%;
  height: 100%;
}
.button:hover::after {
  top: 0;
  background-color: #333;
}
.button:hover {
  color: #fff;
}
</style>
