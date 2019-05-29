<template>
  <div class="column">
    <div class="card">
      <div class="card-image">
        <figure class="image is-4by3">
          <img
            src="https://bulma.io/images/placeholders/1280x960.png"
            alt="Placeholder image"
          />
        </figure>
      </div>
      <div class="card-content">
        <div class="content">
          <b>Card {{ num }}</b> - Lorem ipsum dolor sit amet consectetur
          adipisicing elit. Ea ex doloremque at magnam pariatur.
          <div class="columns is-mobile">
            <div class="column is-half-mobile">
              <a class="button is-info m-t-md">
                <span class="icon">
                  <i class="mdi mdi-twitter"></i>
                </span>
                <span>Twitter</span>
              </a>
            </div>
            <div class="column is-half-mobile">
              <a class="button is-dark m-t-md">
                <span class="icon">
                  <i class="mdi mdi-github-circle"></i>
                </span>
                <span>GitHub</span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["num"]
};
</script>

<style lang="scss" scoped>
</style>