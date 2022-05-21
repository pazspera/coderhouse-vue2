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
            <div class="col-12">
                <p>Elige tu curso</p>
            </div>
            <div class="col">
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" name="checkJavascript" id="checkJavascript">
                    <label class="form-check-label" for="checkJavascript">JavaScript</label>
                </div>
            </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style></style>
