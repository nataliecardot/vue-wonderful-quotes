<template>
  <!-- Bootstrap container class is in App.vue -->
  <div class="row">
    <!-- native modifier tells Vue.js to react to click on component if it happens on native element of this component (the outer div in Quote component template). It says, even though it happened on the HTML code of the component, treat is as if it were a click on app-quote element here (which is not appended to the DOM, only the code in the template is; this workaround is needed). So, it treats clicks on the template as clicks on the component -->
    <app-quote
      v-for="(quote, index) in quotes"
      :key="quote"
      @click.native="deleteQuote(index)"
    >{{ quote }}</app-quote>
  </div>
</template>

<script>
import Quote from "./Quote.vue";

export default {
  // props are passed into QuoteGrid from App.vue file
  props: ["quotes"],
  components: {
    appQuote: Quote,
  },
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    },
  },
};
</script>

<style>
</style>