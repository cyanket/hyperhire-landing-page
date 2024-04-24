<template>
  <q-layout view="lHh Lpr bFf">
    <q-page-container class="main-page" :style="{ height: mainPageHeight }">
      <div class="main-page-content">
        <NavBar />
        <router-view></router-view>
      </div>
    </q-page-container>
    <FooterContainer />
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import NavBar from "../components/NavBar.vue";
import FooterContainer from "../components/FooterContainer.vue";
export default defineComponent({
  name: "MainLayout",
  components: {
    NavBar,
    FooterContainer,
  },
  setup() {
    const mainPageHeight = ref(
      window.innerWidth > 720 ? "926px" : "926px"
    );

    window.addEventListener("resize", () => {
      mainPageHeight.value = window.innerWidth > 720 ? "926px" : "926px";
    });
    return {
      mainPageHeight,
    };
  },
});
</script>

<style lang="scss" scoped>
.main-page {
  position: relative;
  @media (min-width: 600px) {
    background-image: linear-gradient(151.17deg, #26C2B9 8.69%, #288BE7 126.06%), url("/BackgroundImage.png");
    background-size: cover;
  }
  @media (max-width: 599px) {
    background-image: linear-gradient(151.17deg, #26C2B9 8.69%, #288BE7 126.06%), url("/BackgroundImage.png");
    background-size: cover;
    padding-bottom: 980px !important;
  }
  background-position: center;
}

.main-page-content {
  max-width: 1200px;
  margin: 0px auto;
  color: white;
}

.q-toolbar {
  background-color: #3498db;
}
</style>
