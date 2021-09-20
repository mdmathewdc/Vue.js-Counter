<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div class="topnav">

    <!-- use the router-link component for navigation. -->
    <!-- specify the link by passing the `to` prop. -->
    <!-- `<router-link>` will render an `<a>` tag with the correct `href` attribute -->
  
    <router-link to="/">Home</router-link>
    <router-link to="/about">About App</router-link>
    <router-link to="/404">404 Test Page</router-link>
    <p class="heading">Vue.js Counter App</p>
  </div>

    <router-view />

    <img :src="image">
    <!-- <img src="./assets/logo.png"> -->
    <p v-if="inStock"> In stock </p>
    <p v-else>Out of stock</p>

    <p v-show="inStock"> This paragraph will be displayed if the value is true </p>

    <p v-if="inventory > 10"> The inventory is greater than 10 and in stock </p>
    <p v-else-if="inventory <=10 && inventory > 0">Almost sold out! </p>
    <p v-else> Sold out </p>

    <ul>
      <li v-for="detail in details" :key="detail">{{ detail }}</li>
    </ul>

    <div v-for="(variant, index) in variants" :key="variant.id"  class="color-circle" :style="{backgroundColor: variant.color}" @mouseover="updateVariant(index)">{{ variant.color }}</div>
    <!-- @mouseover="updateImage(variant.image)" -->
    <button class="button" v-on:click="addToCart" :disabled= "inStock" :class="{disabledButton: inStock}">Add to cart</button>
    <div class="cart">Cart : {{ cart }}</div>

    <h1>{{ title }}</h1>


  <HelloWorld msg="Vue.js Counter App 1" :premium="premium"/>
  <Counter msg="Counter app message"/>

</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Counter from './components/Counter.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Counter
  },
  data() {
    return {
      premium: true,
      selectedVariant: 0,
      product: 'Socks',
      brand: 'Vue Mastery',
      // image : require('./assets/logo.png'),
      // inStock: true,
      inventory: 100,
      details: ['50% cotton', '30% wool', '20% polyester'],
        variants: [
      { id: 2234, color: 'green', image: require('./assets/green-socks.png'), quantity: 50 },
      { id: 2235, color: 'red', image: require('./assets/red-socks.png'), quantity: 0 }
    ],
    cart: 0
    }
  },
  methods: {
    addToCart() {
      this.cart += 1
    },

    updateImage(variantImage) {

      this.image = variantImage

    },

    updateVariant(index) {
      this.selectedVariant = index
    }
  },
  computed: {
    title() {
      return this.brand + ' ' + this.product
    },
    image () {
  return this.variants[this.selectedVariant].image

    },
    inStock() {
  return this.variants[this.selectedVariant].quantity
  // return true

    }
  }
}
</script>

<style>

.disabledButton {
  background-color: #d8d8d8;
  cursor: not-allowed;

}
.color-circle {
  width: 50px;
  height: 50px;
  margin-top: 8px;
  border: 2px solid #d8d8d8;
  border-radius: 50%;
}

body {
  margin: 0px;
}
.heading {
  color: whitesmoke;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}

/* Add a black background color to the top navigation */
.topnav {
  background-color: #333;
  overflow: hidden;
}

/* Style the links inside the navigation bar */
.topnav a {
  float: left;
  color: #f2f2f2;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
}

/* Change the color of links on hover */
.topnav a:hover {
  background-color: #ddd;
  color: black;
}

/* Add a color to the active/current link */
.topnav a.active {
  background-color: #04AA6D;
  color: white;
}

</style>
