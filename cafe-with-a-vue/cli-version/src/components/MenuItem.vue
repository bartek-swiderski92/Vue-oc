<template>
  <div>
    <img class="menu-item__image" :src="imageSource" :alt="imageAlt" />
    <div>
      <h3>{{ itemName }}</h3>
      <p v-if="isInStock">In Stock</p>
      <p v-else>Out of Stock</p>
      <div>
        <label for="add-item-quantity">Quantity: {{ itemQuantity }}</label>
        <input
          v-model.number="itemQuantity"
          id="add-item-quantity"
          type="number"
        />
        <button @click="addToShoppingCart(itemQuantity)">Add to Shopping Cart</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MenuItem",
  props: [
    addToShoppingCart,
    imageSource,
    imageAlt,
    itemName,
    isInStock,
    itemQuantity
  ]
};
</script>

<style>
</style>