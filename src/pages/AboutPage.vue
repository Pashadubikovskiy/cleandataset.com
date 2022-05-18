<template>
  <MainLayout>
    <section class="hero-block">
      <div class="container hero-block__container">
        <div class="hero-block__text">
          <h1 class="hero-block__title">About us</h1>
          <div class="hero-block__description">
            CleanDataSet is a commodities data provider for natural gas,
            electricity, weather, oil, and cryptocurrency. Our extensive data
            sets include nominations data for natural gas, as well as over
            35,000 locational marginal electricity prices. We are always seeking
            to expand our data collections and deliver the best experience for
            our customers. For each dataset, a free 30 day trial is available
            for your evaluation. In addition, we are ready to answer any
            inquiries about our company and service through our contact page.
          </div>
        </div>
        <div class="hero-block__image">
          <img
            src="../assets/images/about/hero.svg"
            alt="Dataset for your project"
          />
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
@import "../assets/styles/pages/about";
</style>
