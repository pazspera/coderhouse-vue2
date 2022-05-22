<template>
  <div id="app">
    <WebForm v-show="false" />
    <VuelidateTest />
  </div>
</template>

<script>
import WebForm from "@/components/WebForm.vue";
import VuelidateTest from "@/components/VuelidateTest.vue";

export default {
  name: "App",
  components: {
    WebForm,
    VuelidateTest
  },
};
</script>

<style>
#app{
  margin: 3rem 0;
}
</style>
