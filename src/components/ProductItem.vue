<template>
  <div class="product-item">
    <img :src="`/assets/${product.image}`" :alt="product.name" class="product-image" />
    <h3>{{ product.name }}</h3>
    <p class="product-description">{{ product.description }}</p>
    <div class="product-rating">
      <span v-for="star in Math.floor(product.rating)" :key="`full-${star}-${product.id}`" class="filled-star">&#9733;</span>
      <span v-if="product.rating % 1" class="half-star">&#9734;</span>
      <span v-for="star in 5 - Math.ceil(product.rating)" :key="`empty-${star}-${product.id}`" class="empty-star">&#9734;</span>
    </div>
    <p v-if="product.discountPrice" class="product-discount-price">{{ product.discountPrice }} € (Sale!)</p>
    <p v-else class="product-price">{{ product.price }} €</p>
  </div>
</template>




<script>
export default {
  name: 'ProductItem',
  props: {
    product: Object
  }
};
</script>

<style>
.product-item {
  border: 1px solid #4d2a2a;
  border-radius: 8px;
  padding: 1rem;
  margin: 1rem;
  width: 400px;
  text-align: center;
}

.product-image {
  max-width: 100%;
  height: auto;
  margin-bottom: 1rem;
}

.product-description {
  min-height: 60px;
}

.product-rating {
  color: #ffd700;
  font-size: 2rem;
  margin-bottom: 0.5rem;
}

.filled-star {
  color: #ffd700;
}

.half-star:before {
  content: "\\2605";
  position: absolute;
  display: inline-block;
  color: #ffd700;
  clip-path: polygon(0 0, 50% 0, 50% 100%, 0% 100%);
}

.empty-star {
  color: #ccc;
}

.product-price {
  color: green;
  font-weight: bold;
  font-size: 1.2rem;
  margin-top: 0.5rem;
}
</style>