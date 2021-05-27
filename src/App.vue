<template>
  <div class="container">
    <app-header :maxQuotes="maxQuotes" :quotesCount="quotes.length"></app-header>

    <new-quote @quoteWasAdded="addNewQuote" ></new-quote>
    <quotes-grid :quotes="quotes" @quoteDeleted="deleteQuote"></quotes-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info:Click on a quote to delete it
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuotesGrid from "./components/QuotesGrid.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";

export default {
  components: {NewQuote, QuotesGrid,appHeader:Header},
  data: function () {
    return {
      maxQuotes: 10,
      quotes: ['Just to see something']
    }
  },
  methods:{
    addNewQuote(quote){
      if(this.quotes.length>=10){
        return alert('Please delete quotes first')
      }
      this.quotes.push(quote)
    },
    deleteQuote(index) {
      console.log('yes',1)
      this.quotes.splice(index,1)
    }
  }
}
</script>

<style>
</style>
