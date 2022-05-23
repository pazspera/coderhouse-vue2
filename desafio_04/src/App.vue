<template>
  <div id="app">
    <WebForm />
    <!-- <VuelidateTest v-show="false"/> -->
    <!-- <VuelidateTest2 /> -->
  </div>
</template>

<script>
import WebForm from "@/components/WebForm.vue";
/* import VuelidateTest from "@/components/VuelidateTest.vue"; */
/* import VuelidateTest2 from "@/components/VuelidateTest2.vue"
 */
export default {
  name: "App",
  components: {
    WebForm,
    /* VuelidateTest,  */
    /* VuelidateTest2 */
  },
};
</script>

<style>
#app{
  margin: 3rem 0;
}
</style>
