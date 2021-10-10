<template>
  <div class="container">
    <h1 class="ml10">
      <span class="text-wrapper">
        <span class="letters">WELCOME!</span>
      </span>
    </h1>
  </div>
</template>

<script>
export default {
  name: "Welcome",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.ml10 {
  position: relative;
  font-weight: 800;
  font-size: 3.5em;
}

.ml10 .text-wrapper {
  position: relative;
  display: inline-block;
  overflow: hidden;
}

.ml10 .letter {
  display: inline-block;
  line-height: 1em;
  transform-origin: 0 0;
}
</style>
