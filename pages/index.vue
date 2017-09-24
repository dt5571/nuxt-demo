<template>
  <section class="container">
    <div>
      <h1 class="title">
        电影数目 {{count}}
      </h1>
      <ul class="movie-lists">
        <li class="movie-list"  v-for="movie in subjects" v-on:click="clickTest(movie)">
          <h2 class="movie-title">{{movie.title}}</h2>
          <img  :src="movie.images.medium" alt="">
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
import Vue from 'vue'
import VueRouter from 'vue-router'
import axios from 'axios'
Vue.use(VueRouter)

export default {
  asyncData ({ params }) {
    return axios.get(`https://api.douban.com/v2/movie/in_theaters`)
      .then((res) => {
        return { count: res.data.count, subjects: res.data.subjects || [] }
      })
  },
  methods: {
    clickTest (movie) {
      this.$router.push({ path: `/detail/${movie.id}` })
    }

  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
.movie-lists {
  width: 100%;
}
.movie-list {
  list-style: none;
  float: left;
  width: 21%;
  background: #ccc;
  /*margin: 10px auto;*/
  margin: 2%;
}

</style>
