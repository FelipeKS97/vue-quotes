<template>
  <div class="container">
      <NewQuote @AddQuote="newQuote"></NewQuote>
     <QuoteGrid :quotes="quotes"></QuoteGrid>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import QuoteGrid from './components/QuoteGrid.vue'
import NewQuote from './components/NewQuote.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    QuoteGrid,
    NewQuote
  },
  methods: {
    newQuote(quote) {
      this.quotes.push(quote)
    }
  },
  data () {
    return {
      quotes: ['Just quote'],
      maxQuotes: 10,
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
