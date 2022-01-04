<template>
  <a @click="itemClick" :class="{ on: tag === ordered }">
    {{ navName }}
  </a>
</template>

<script>
export default {
  props: ["tag", "ordered", "navName"],
  created() {
    console.log("navItem", this.tag, this.ordered);
  },
  methods: {
    itemClick() {
      this.$emit("onNavItemClick", this.tag);
    },
  },
};
</script>

<style scoped>
.on {
  color: red;
}
</style>