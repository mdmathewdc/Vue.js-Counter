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

    <img :src="imagePath">
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

    <div v-for="variant in variants" :key="variant.id">{{ variant.color }}</div>



  <HelloWorld msg="Vue.js Counter App"/>
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
      imagePath : require('./assets/logo.png'),
      inStock: true,
      inventory: 100,
      details: ['50% cotton', '30% wool', '20% polyester'],
        variants: [
      { id: 2234, color: 'green' },
      { id: 2235, color: 'blue' }
    ]
    }
  }
}
</script>

<style>

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
