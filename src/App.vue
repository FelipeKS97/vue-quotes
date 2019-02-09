<template>
  <div class="container">
      <Header :quoteCount="quotes.length" :maxQuotesNumber="maxQuotesNumber"></Header>
      <NewQuote @AddQuote="newQuote"></NewQuote>
      <QuoteGrid @quoteDelete="deleteQuote" :quotes="quotes"></QuoteGrid>
      <div class="row">
        <div class="col-sm-12 text-center">
          <div class="alert alert-info">Info: Click on a quote and delete it!</div>
        </div>
      </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import QuoteGrid from './components/QuoteGrid.vue'
import NewQuote from './components/NewQuote.vue'
import Header from './components/Header.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    QuoteGrid,
    NewQuote,
    Header
  },
  methods: {
    newQuote(quote) {
      if(this.quotes.length >= this.maxQuotesNumber) {
        return alert('Please, remove remaining quotes, limit reached')
      }
      this.quotes.push(quote)
    }, 
    deleteQuote(index) {
      this.quotes.splice(index, 1)
    }
  },
  data () {
    return {
      quotes: ['Just quote'],
      maxQuotesNumber: 10,
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
