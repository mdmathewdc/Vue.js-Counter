 <template>
  <div>
    <h2>Counter: {{ count }}</h2>

    <button @click="increment" class="blue-button">Click to Incrementtrtrtr</button>
    <button @click="decrement" class="blue-button">Click to Decrement</button>
    <button v-on:click="reset" class="red-button">Reset</button>


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
      reset() {
          this.count = 0;
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button {
  margin: 10px;
}
.blue-button {
  background-color: #189fdd; /* Blue */
  border: none;
  color: white;
  padding: 5px 10px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}

.red-button {
  background-color: #f7542c; /* Red */
  border: none;
  color: white;
  padding: 5px 10px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}

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
