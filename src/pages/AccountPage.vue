<template>
  <MainLayout>
    <section class="hero-block">
      <div class="container hero-block__container">
        <div class="hero-block__inner hero-block-inner">
          <div class="hero-block-inner__image">
            <img
              src="../assets/images/circle.svg"
              alt="Dataset for your project"
            />
          </div>
          <router-view></router-view>
        </div>
      </div>
    </section>
  </MainLayout>
</template>

<script>
import MainLayout from "../layouts/MainLayout.vue";
export default {
  components: {
    MainLayout,
  },
};
</script>

<style scoped lang="scss">
@import "../assets/styles/pages/account";
</style>
