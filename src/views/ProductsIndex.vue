<template>
  <div class="products-index">
    <h1>{{ message }}</h1>
    <div class="row">
      <div class="col-sm-4" v-for="product in products">
        <div class="card">
          <img style="width: 200px" v-bind:src="product.images[0]&&product.images[0].url" class="card-img-top" alt="...">
          <div class="card-body">
            <h3 class="card-title">{{product.name}}</h3>
            <p class="card-text">Price: {{product.price}}</p>
            <p class="card-text">{{product.description}}</p>
            <a href="#" class="btn btn-primary">Product details</a>
          </div>
        </div>
      </div>
      <!-- <p>Description: {{product.description}}</p> -->
      <!-- <p>{{product.images}}</p> -->
      <!-- <p>{{product.images[0].url}}</p> -->
    </div>

  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

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
    indexProducts: function () {
      axios.get("/api/products").then((response) => {
        console.log(response.data);
        this.products = response.data;
      });
    },
  },
};
</script>

