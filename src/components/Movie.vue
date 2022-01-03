<template>
  <div class="movie">
    <nav class="nav">
      <ul class="tab">
        <li v-for="(item, index) in _navList" :key="index">
          <a @click="clickOrdering(item)">
            {{ item }}
          </a>
        </li>
      </ul>
      <FilteredMovieList :movies="movies" />
    </nav>
  </div>
</template>

<script>
import FilteredMovieList from "./FilteredMovieList.vue";
export default {
  name: "Movie",
  components: { FilteredMovieList },
  computed: {
    _navList() {
      return Object.keys(this.navList);
    },
  },
  data() {
    return {
      ordered: "예매순",
      navList: {
        예매순: "ticketing",
        평점순: "score",
        개봉일순: "openDate",
        주말관객순: "week",
        다운로드순: "rate",
      },
      movies: [
        {
          name: "남애의 여름밤",
          src: "mov_1.jpg",
          rate: 15,
          score: 9.43, //평점
          sale: 11.7, //판매율
          openDate: 8.26, //개봉일
          ticketing: 11.79, //예매율
          week: 8777, //주말관객
        },
        {
          name: "시크릿 가든",
          src: "mov_2.jpg",
          rate: 0,
          score: 8.13,
          sale: 7.7, //판매율
          openDate: 9.3, //개봉일
          ticketing: 20.66,
          week: 2000,
        },
        {
          name: "반도",
          src: "mov_3.jpg",
          rate: 15,
          score: 8.54,
          sale: 7.7,
          openDate: 9.3,
          ticketing: 9.79,
          week: 23327,
        },
        {
          name: "강철비2",
          src: "mov_4.jpg",
          rate: 19,
          score: 7.43,
          sale: 7.7,
          openDate: 9.7,
          ticketing: 8.6,
          week: 23421,
        },
        {
          name: "신혼여행 허리케인",
          src: "mov_5.jpg",
          rate: 12,
          score: 6.2,
          sale: 10.7,
          openDate: 8.17,
          ticketing: 2.11,
          week: 3213,
        },
        {
          name: "테넷",
          src: "mov_6.jpg",
          rate: 19,
          score: 7.12,
          sale: 9.11,
          openDate: 11.17,
          ticketing: 3.21,
          week: 3213,
        },
        {
          name: "오케이 마담",
          src: "mov_7.jpg",
          rate: 20,
          score: 9.43,
          sale: 9.11,
          openDate: 9.1,
          ticketing: 3.79,
          week: 2277,
        },
        {
          name: "다만 악에서 구하소서",
          src: "mov_8.jpg",
          rate: 20,
          score: 8.9,
          sale: 8.8,
          openDate: 8.21,
          ticketing: 12.79,
          week: 83777,
        },
      ],
    };
  },
  methods: {
    clickOrdering(name) {
      this.ordered = this.navList[name];
      console.log(this.ordered);

      this.movies.sort((a, b) => {
        return b[this.ordered] - a[this.ordered];
      });
    },
  },
};
</script>

<style>
.movie {
  width: 590px;
  margin: 30px auto 0;
  padding: 10px;
  background-color: #242424;
  /* background-color: white; */
  overflow: hidden;
}
.nav ul {
  display: flex;
  justify-content: space-between;
}

.movie .tab {
  text-align: center;
  font-size: 16px;
}
.movie .tab > li {
  display: inline-block;
  margin: 0 20px;
}
.movie .tab > li.on a {
  color: red;
}
</style>