<template>
  <div>
    <p v-for="item in this.$store.state.ask" v-bind:key="item.id">
      <router-link v-bind:to="`item/${item.id}`">
        {{ item.title }}
      </router-link>
      <small>{{ item.time_ago }} by {{ item.user }}</small>
    </p>
  </div>
</template>

<script>
// import { fetchAskList } from "../api/index.js";
import { mapState } from "vuex";
// import { mapGetters, mapState } from "vuex";
export default {
  computed: {
    // #3
    //...mapGetters(["fetchedAsk"]),
    // #2
    ...mapState({
      ask: (state) => state.ask,
    }),

    // #1
    // ask() {
    //   return this.$store.state.ask;
    // }
  },
  created() {
    this.$store.dispatch("FETCH_ASK");
  },
};
</script>

<style></style>
