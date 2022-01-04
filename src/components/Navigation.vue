<template>
  <nav class="nav">
    <ul class="tab">
      <li v-for="(navName, index) in _navList" :key="index">
        <NavItem
          v-bind:tag="navList[navName]"
          v-bind:navName="navName"
          v-bind:ordered="ordered"
          v-on:onNavItemClick="onNavItemClick"
        />
      </li>
    </ul>
  </nav>
</template>

<script>
import NavItem from "./NavItem.vue";
export default {
  components: { NavItem },
  props: ["_navList", "ordered", "navList"],
  methods: {
    onNavItemClick(item) {
      this.$emit("clickOrdering", item);
    },
  },
  data() {
    return {
      tag: "",
    };
  },
};
</script>

<style scoped>
.nav ul {
  display: flex;
  justify-content: space-between;
  padding: 0 35px;
}

.movie .tab {
  text-align: center;
  font-size: 16px;
}
.movie .tab > li {
  display: inline-block;
  margin: 0 20px;
  cursor: pointer;
}
</style>