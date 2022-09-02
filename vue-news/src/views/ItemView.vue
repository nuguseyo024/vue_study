<template>
  <p>{{ this.$store.state.item.title }}</p>
</template>

<script>
export default {
  created() {
    const itemId = this.$route.params.id;
    this.$store.dispatch("FETCH_ITEM", itemId);
  },
};
</script>

<style></style>
