 <template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>{{ premium }}</h2>
    <p>Shipping - {{ shipping }}</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: {
      type: String,
      required: true
    },
    premium: {
      type: Boolean,
      required: true
    }
  },
  computed: {
    shipping() {
   if (this.premium) {
      return 'Free'
    }
      return 2.99
    }
 
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
