<template>
  <div class="ыв">
    <the-header></the-header>
    <div class="l">
      <the-main></the-main>
      <the-footer></the-footer>
    </div>
  </div>
</template>

<script>
import TheFooter from "./components/TheFooter.vue";
import TheHeader from "./components/TheHeader.vue";
import TheMain from "./components/TheMain.vue";
export default {
  components: {
    TheFooter,
    TheHeader,
    TheMain,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Nunito:wght@700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Nunito:wght@700&family=Open+Sans:wght@400;600&display=swap");

* {
  margin: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif, "Open Sans";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #222222;
  min-width: 320px;
  margin: 0 auto;
  display: grid;
  grid-template-rows: 130px minmax(calc(100vh - 260px), auto) 130px;
  padding: 0 10px;
  box-sizing: border-box;
}

@media screen and (min-width: 768px) {
  #app {
    padding: 0 20px;
  }
}

@media screen and (min-width: 1280px) {
  #app {
    padding: 0;
  }
}

.l {
  margin: 0 auto;
  max-width: 1280px;
}
</style>
