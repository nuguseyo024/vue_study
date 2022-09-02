<template>
  <div>
    <p v-for="item in this.$store.state.jobs" v-bind:key="item.id">
      <a :href="item.url">
        {{ item.title }}
      </a>
      <small>- {{ item.domain }}</small>
    </p>
  </div>
</template>

<script>
// import { fetchJobsList } from "../api/index.js";
export default {
  created() {
    this.$store.dispatch("FETCH_JOBS");
  },
};
</script>

<style></style>
