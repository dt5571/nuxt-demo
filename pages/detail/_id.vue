<template>
  <section>
    我是电影详情页
    <h2>电影名称:{{movie.title}}</h2>
    <div>地区:{{movie.countries}}</div>
    <div>电影类型:{{movie.genres}}</div>
    <!--<div><img :src="movie.images.large" alt=""></div>-->
    <p>电影概要:{{movie.summary}}</p>
  </section>
</template>

<script>
import axios from 'axios';
export default {
  asyncData({params}) {
    return axios.get(`http://localhost:3000/v2/movie/subject/${params.id}`)
      .then((res) => {
        return {movie: res.data};
      });
  },
  methods: {

  },
};
</script>


