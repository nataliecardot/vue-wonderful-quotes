<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <!-- newQuote($event) is implicitly passed, where $event refers to data passed in custom event -->
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Click on a quote to delete it.</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";

export default {
  data() {
    return {
      quotes: ["Inspiring quote"],
      maxQuotes: 10,
    };
  },
  methods: {
    // Vue.js automatically provides data passed on custom event, so can simply access the quote passed by NewQuote.vue in the emit event in the argument
    newQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert("Please delete a quote first.");
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      // Modify existing array by removing one element at index passed by custom emit event on QuoteGrid.vue
      this.quotes.splice(index, 1);
    },
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: Header,
  },
};
</script>

<style></style>
