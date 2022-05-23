<template>
  <div id="app">
    <FormWeb />
  </div>
</template>

<script>
import FormWeb from "@/components/FormWeb.vue";

export default {
  name: "App",
  components: {
    FormWeb,
  },
};
</script>

<style>
#app{
  margin: 3rem 0;
}
</style>
