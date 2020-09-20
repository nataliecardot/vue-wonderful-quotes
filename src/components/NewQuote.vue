<template>
  <!-- Bootstrap container class is in App.vue -->
  <div class="row">
    <form action>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <label for="quote">Quote</label>
        <textarea id="quote" rows="3" class="form-control" v-model.trim="quote"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <!-- Using prevent modifier because don't want to submit the form; don't want to send request to server, which would reload page -->
        <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Set whenever something is written in textarea
      quote: "",
    };
  },
  methods: {
    createNew() {
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    },
  },
};
</script>

<style>
</style>