<template>
  <dvi>
    <div class="header">
      <span class="go-back" @click="goBack()">返回</span>
    </div>
    <div>
      <nuxt/>
    </div>
  </dvi>
</template>


<script>
  export default {
    methods: {
      goBack() {
        console.log('goback');
        history.go(-1);
      },
    },
  };
</script>
<style>
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*, *:before, *:after {
  box-sizing: border-box;
  margin: 0;
}
.header {
  width: 100%;
  height: 50px;
  line-height: 50px;
  background: #1c8bd0;
  text-indent: 10px;
}
.go-back {
  color: #f7f8fb;
  font: 20px;
}
.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
