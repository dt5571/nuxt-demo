<template>
  <section class="container">
    我是电影详情页 {{id}}
  </section>
</template>

<script>
  import Vue from 'vue'
  import VueRouter from 'vue-router'
  import axios from 'axios'
  Vue.use(VueRouter)
  export default {
    asyncData ({ params }) {
      return axios.get(`https://api.douban.com/v2/movie/subject/1764796`)
        .then((res) => {
          console.log(res)
          return { id: res.data.id }
        })
    },
    methods: {

    }
  }
</script>


