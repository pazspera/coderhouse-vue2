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
        <!-- País de residencia -->
        <div class="row mb-3">
          <div class="col">
            <p class="form-label">País de residencia</p>
            <select class="form-select" name="country" id="country">
              <option selected></option>
              <option v-for="country in countriesList" :key="country.id" :value="country.name">{{ country.name }}</option>
            </select>
          </div>
        </div>
        <!-- Cursos -->
        <div class="row mb-3">
          <div class="col">
            <p class="form-label">Cursos disponibles</p>
            <div class="form-check" v-for="(course, c) in availableCourses" :key="c">
              <input class="form-check-input" type="checkbox" :name="course.id" :id="course.id" />
              <label class="form-check-label" :for="course.id">{{ course.name }}</label>
            </div>
          </div>
        </div>
        <!-- Comentarios -->
        <div class="row mb-3">
          <div class="col">
            <label for="comments" class="form-label">Comentarios</label>
            <textarea class="form-control" id="comments" rows="3"></textarea>
          </div>
        </div>
        <!-- Newsletter -->
        <div class="row mb-3">
            <div class="col">
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" name="newsletter" id="newsletter">
                    <label class="form-check-label" for="newsletter">Suscribime al newsletter</label>
                </div>
            </div>
        </div>
        <!-- Submit -->
        <button type="submit" class="btn btn-primary">Enviar</button>
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
      countriesList: [
        {
          id: "a",
          name: "Argentina",
        },
        {
          id: "b",
          name: "Uruguay",
        },
        {
          id: "c",
          name: "Chile",
        },
        {
          id: "d",
          name: "Perú",
        },
        {
          id: "e",
          name: "Mexico",
        },
      ],
    };
  },
};
</script>

<style scoped>
.container {
  max-width: 700px;
}
</style>
