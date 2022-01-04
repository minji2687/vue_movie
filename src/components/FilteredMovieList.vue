<template>
  <ol>
    <li v-for="(movie, index) in movies" :key="index">
      <!-- {{ movies }} -->
      <a href="">
        <h4 class="hide">{{ movie.name }}</h4>
        <span class="hide rate" :class="`rate${movie.rate}`">{{
          movie.rate
        }}</span>
        <strong class="rank">{{ index }}</strong>
        <img
          class="poster"
          :src="require(`@/assets/${movie.src}`)"
          alt="남애의여름밤"
        />
        <!--  -->
        <span class="desc">
          <!-- <i class="star"><b style="width: 94%"></b></i> -->
          <i class="star"><b :style="`width:${movie.score * 10}%`"></b></i>
          <em class="score">{{ movie.score }}</em>
        </span>
      </a>
    </li>
  </ol>
</template>

<script>
import startImg from "@/assets/icon_star.png";
export default {
  props: ["movies"],
};
</script>

<style scoped>
ol > li .hide {
  font-size: 0;
}
ol > li {
  float: left;
  width: 125px;
  height: 204px;
  margin: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.4);
  border: 1px solid rgba(255, 255, 255, 0.2);
}
ol > li a {
  display: block;
  position: relative;
}
ol > li .rank {
  position: absolute;
  top: 5px;
  left: 5px;
  font-size: 24px;
  font-style: italic;
  color: white;
  text-shadow: 0 0 10px black;
}
.movie > ol > li .rate {
  position: absolute;
  top: 5px;
  right: 5px;
  content: "";
  width: 25px;
  height: 25px;
  display: block;
  /* background-image: url("../images/icon_rate.png"); */
  background-image: url("~@/assets/icon_rate.png");
  background-repeat: no-repeat;
}

ol > li .rate15 {
  background-position: 0 -60px;
}
ol > li .rate12 {
  background-position: 0 -30px;
}
ol > li .rate00 {
  background-position: 0 0;
}
ol > li .rate19 {
  background-position: 0 -120px;
}
ol > li .rate20 {
  background-position: 0 -90px;
}
ol > li .desc {
  position: relative;
  background-color: black;
  display: block;
  height: 25px;
}
ol > li i {
  float: left;
  margin: 5px 0 0 10px;
  font-style: normal;
}
ol > li em {
  float: right;
  margin: 5px 10px 0 0;
  font-weight: bold;
  font-style: normal;
}
ol > li i.star {
  width: 71px;
  height: 14px;
  background: url("~@/assets/icon_star.png") no-repeat 0 0/71px auto;
}
ol > li i.star > b {
  display: block;
  width: 0;
  height: 100%;
  /* background: url("../images/icon_star.png") no-repeat 0 -15px/71px auto; */
  background: url("~@/assets/icon_star.png") no-repeat 0 -15px/71px auto;
}
ol > li i.reserv_title {
  font-weight: bold;
}
ol > li em.reserv_num {
  color: red;
}
ol > li i.open_title {
  position: absolute;
  right: 35px;
  font-weight: bold;
  color: red;
}
ol > li em.open_num {
  font-weight: bold;
}
ol > li i.week_title {
  font-weight: bold;
}
ol > li em.week_num {
  color: red;
}
ol > li i.sale_title {
  font-weight: bold;
}
ol > li em.sale_num {
  color: red;
}
.tab {
  text-align: center;
  font-size: 16px;
}
.tab > li {
  display: inline-block;
  margin: 0 20px;
}
.tab > li.on a {
  color: red;
}
</style>