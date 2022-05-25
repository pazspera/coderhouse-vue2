<template>
  <form @submit.prevent="submitForm">
    <div class="form-group">
      <label for="name">Name:</label>
      <input type="text" id="name" v-model="form.name" />
      <p>Name: {{ form.name }}</p>
      <p v-if="!nameIsValid" class="text-danger">The name is required</p>
    </div>
    <div class="form-group">
      <label for="age">Age:</label>
      <input type="number" id="age" v-model.number="form.age" />
      <p>Age: {{ form.age }}</p>
      <p v-if="!ageIsValid" class="text-danger">The age is invalid</p>
    </div>
    <button :disabled="!formIsValid">Submit</button>
  </form>
</template>

<script>
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
  methods: {
    submitForm() {
      if (this.formIsValid) {
        console.log("Form Submitted", this.form);
      } else {
        console.log("Invalid Form");
      }
    },
  },
  computed: {
    nameIsValid() {
      // Convierte el valor a booleano con el !!
      return !!this.form.name;
    },
    ageIsValid() {
      return typeof this.form.age === "number" && this.form.age > 12 && this.form.age < 120;
    },
    formIsValid() {
        return this.nameIsValid && this.ageIsValid;
    }
  },
};
</script>

<style scoped>
.container {
  max-width: 500px;
  text-align: left;
}
</style>
