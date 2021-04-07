<template>
  <div class="home">
    <h1>{{ message }}</h1>

  </div>
</template>

<style>
</style>

<script>
export default {
  data: function () {
    return {
      message: "All Products",
      products: [],
    };
  },
  created: function () {
    this.indexProducts();
  },
  methods: {
    indexProducts: function () {},
  },
};
</script>

