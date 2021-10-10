<template>
  <div id="app">
    <Welcome />
    <Form />
  </div>
</template>

<script>
import Welcome from "./components/Welcome.vue";
import Form from "./components/Form.vue";
export default {
  name: "App",
  components: {
    Welcome,
    Form,
  },
};
</script>

<style>
#app {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
</style>
