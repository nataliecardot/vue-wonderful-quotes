<template>
  <!-- Bootstrap container class is in App.vue -->
  <div class="col-sm-6 col-md-4 col-lg-3">
    <!-- Cards replaced panels in Bootstrap 4 -->
    <div class="panel panel-default">
      <div class="panel-body quote">
        <!-- Using a slot because quote content will come from outside; the thing passing in the content/its holder (in this case quote grid component) should be deciding how it looks -->
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["quotes"],
};
</script>

<style>
.panel-body {
  font-family: "Arizonia", cursive;
  font-size: 24px;
  color: #6e6e6e;
}

.quote {
  cursor: pointer;
}

.quote:hover {
  background-color: #ffe2e2;
}
</style>