<template>
  <div>
    <app-progress-bar :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-progress-bar>
    <app-new-quote @addNewQuote="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
    <div class="alert alert-info text-center">Info: Click on a Quote to delete it</div>
  </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid'
import NewQuote from './components/NewQuote'
import ProgressBar from './components/ProgressBar'

export default {
  data: function() {
    return {
      quotes: ['Vue JS'],
      maxQuotes: 10
    }
  },
  methods: {
    newQuote(quote) {
      if(this.quotes.length >= this.maxQuotes) {
        alert('Please delete an item!')
        return
      }
      this.quotes.push(quote)
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1)
    }
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appProgressBar: ProgressBar
  }
}

</script>

<style>
  
</style>