<template>
  <div id="app">
    <WebForm />
  </div>
</template>

<script>
import WebForm from "@/components/WebForm.vue";

export default {
  name: "App",
  components: {
    WebForm
  },
};
</script>

<style>
#app{
  margin: 3rem 0;
}
</style>
