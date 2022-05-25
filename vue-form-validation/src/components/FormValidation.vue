<template>
  <form @submit.prevent="submitForm">
    <div class="form-group">
      <label for="name">Name:</label>
      <input type="text" id="name" v-model="form.name" />
      <p>Name: {{ form.name }}</p>
      <p v-if="$v.form.name.$invalid" class="text-danger">The name is required</p>
    </div>
    <div class="form-group">
      <label for="age">Age:</label>
      <input type="number" id="age" v-model.number="form.age" />
      <p>Age: {{ form.age }}</p>
      <p v-if="$v.form.name.$invalid" class="text-danger">The age is invalid</p>
    </div>
    <button :disabled="$v.form.$invalid">Submit</button>
  </form>
</template>

<script>
import { required, integer, between } from "vuelidate/lib/validators";

export default {
  name: "FormValidation",
  data() {
    return {
      form: {
        name: "",
        age: 0,
      },
    };
  },
  validations: {
    form: {
      name: {
        required: required,
      },
      age: {
        required: required,
        integer: integer,
        between: between(12, 120)
      },
    },
  },
  methods: {
    submitForm() {
      if (!this.$v.form.$invalid) {
        console.log("Form Submitted", this.form);
      } else {
        console.log("Invalid Form");
      }
    },
  },
};
</script>

<style scoped>
.container {
  max-width: 500px;
  text-align: left;
}
</style>
