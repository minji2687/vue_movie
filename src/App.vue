<template>
  <div id="app">
    <Movie />
  </div>
</template>

<script>
import Movie from "./components/Movie";

export default {
  name: "App",
  components: {
    Movie,
  },
};
</script>

<style>
body {
  font: normal 12px Arial, sans-serif;
  line-height: 1.3;
  color: #666666;
  background-color: #fff;
  margin: 0;
  padding: 0;
}
h1,
h2,
h3,
h4,
h5,
h6 {
  font-size: 1em;
}
h1,
h2,
h3,
h4,
h5,
h6,
div,
p,
dl,
dt,
dd,
ul,
ol,
li,
form,
fieldset,
blockquote,
address,
table,
thead,
tbody,
tfoot,
tr,
td,
caption {
  margin: 0;
  padding: 0;
}
li {
  list-style: none;
}
a {
  text-decoration: none;
  color: white;
}

/* movie */
body {
  background-color: #242424;
}
</style>
