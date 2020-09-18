<template>
  <div class="container">
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes"></app-quote-grid>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";

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
      this.quotes.push(quote);
    },
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
  },
};
</script>

<style></style>
