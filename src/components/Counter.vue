 <template>
  <div class="hello2">
    <h1>{{ msg }}</h1>
    <p>
      Current counter : {{ count }}
    </p>
    <button @click="increment">Click to Increment</button>
    <button @click="decrement">Click to Decrement</button>
    <button v-on:click="reverseMessage">Click me</button>


  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
      return {
          count: 0  
      }
  },
  methods: {
      increment() {
          this.count += 1;
      },
      decrement() {
          this.count -= 1;
      },
      reverseMessage() {
          this.count = 100;
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
p {
  color: red;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
