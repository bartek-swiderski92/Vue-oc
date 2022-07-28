<template>
  <div id="app">
 <h1>{{ restaurantName }}</h1>
      <p class="description">
        Welcome to {{ restaurantName }}! We are known for our freshly baked
        bread and french pastries! Give you morning a warm start or treat
        yourself in the middle of the day. Our butter is imported from local
        farmers in France. Once you take your first bite, you will see why
        everyone can't get enough!
      </p>

      <section class="menu">
        <h2>Menu</h2>
        <div v-for="item in simpleMenu" :key="item.name" class="menu-item">
          <img
            class="menu-item__image"
            :src="item.image.source"
            :alt="item.image.alt"
          />
          <div>
            <h3>{{ item.name }}</h3>
            <p v-if="item.inStock">In Stock</p>
            <p v-else>Out of Stock</p>
            <div>
              <label for="add-item-quantity"
                >Quantity: {{ item.quantity }}</label
              >
              <input
                v-model.number="item.quantity"
                id="add-item-quantity"
                type="number"
              />
              <button @click="addToShoppingCart(item.quantity)">
                Add to Shopping Cart
              </button>
            </div>
          </div>
        </div>
      </section>

      <aside class="shopping-cart">
        <h2>Shopping Cart: {{ shoppingCart }} items</h2>
      </aside>

      <h2>Contact Us</h2>
      <p>Address: {{ address }}</p>
      <p>Phone: {{ phone }}</p>
      <p>Email: {{ email }}</p>
      <p>Hours:</p>
      <ul>
        <li>M-F: 06:00 to 16:00</li>
        <li>Saturday: 07:00 to 14:00</li>
        <li>Sunday: 07:00 to 12:00</li>
      </ul>
      <footer class="footer">
        <p>{{ copyright }}</p>
      </footer>
  </div>
</template>

<script>

export default {
  name: 'app',
  components: {

  },
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
