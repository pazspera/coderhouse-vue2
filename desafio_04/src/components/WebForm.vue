<template>
  <div>
    <div class="container">
      <form>
        <!-- Nombre y apellido -->
        <div class="row mb-3">
          <div class="col">
            <label class="form-label" for="name">Nombre</label>
            <input type="text" class="form-control" name="name" id="name" />
          </div>
          <div class="col">
            <label class="form-label" for="lastName">Apellido</label>
            <input type="text" class="form-control" name="lastName" id="lastName" />
          </div>
        </div>
        <!-- Email -->
        <div class="row mb-3">
          <div class="col">
            <label class="form-label" for="email">Email</label>
            <input class="form-control" type="email" name="email" id="email" />
          </div>
        </div>
        <!-- Cursos -->
        <div class="row mb-3">
          <div class="col">
            <p>Cursos disponibles</p>
            <div class="form-check" v-for="(course, c) in availableCourses" :key="c">
              <input class="form-check-input" type="checkbox" :name="course.id" :id="course.id" />
              <label class="form-check-label" :for="course.id">{{ course.name }}</label>
            </div>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "WebForm",
  data() {
    return {
      availableCourses: [
        {
          id: "checkJavascript",
          name: "JavaScript",
        },
        {
          id: "checkVue",
          name: "Vue",
        },
        {
          id: "checkReact",
          name: "React",
        },
        {
          id: "checkAngular",
          name: "Angular",
        },
        {
          id: "checkNode",
          name: "NodeJS",
        },
      ],
    };
  },
};
</script>

<style></style>
