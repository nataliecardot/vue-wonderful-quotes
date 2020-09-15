<template>
  <!-- Bootstrap container class is in App.vue -->
  <div class="row">
    <app-quote v-for="quote in quotes" :key="quote">{{ quote }}</app-quote>
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
};
</script>

<style>
</style>