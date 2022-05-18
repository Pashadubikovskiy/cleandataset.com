<template>
  <MainLayout>
    <div v-if="dataset.page" class="dataset-page">
      <section
        class="dataset-page__hero dataset-hero"
        :class="`dataset-hero--${dataset.color}`"
      >
        <div class="container dataset-hero__container">
          <div class="dataset-hero__text">
            <h2 class="dataset-hero__title">
              {{ dataset.page.title }}
            </h2>
            <p class="dataset-hero__description">
              {{ dataset.page.description }}
            </p>
          </div>
          <div class="dataset-hero__image">
            <img :src="dataset.page.iconUrl" :alt="dataset.page.title" />
          </div>
        </div>
      </section>

      <section class="dataset-page__section dataset-section">
        <div class="container dataset-section__container">
          <div class="dataset-section__text dataset-section-text">
            <h3 class="dataset-section-text__title">
              {{ dataset.page.listTitle }}
            </h3>

            <ul class="dataset-section-text__list">
              <li v-for="item in dataset.page.list" :key="item.boldText">
                <strong>{{ item.boldText }}</strong>
                {{ item.text }}
              </li>
            </ul>
          </div>

          <div class="dataset-section__aside dataset-aside">
            <div class="dataset-aside__logo">
              <img src="../assets/images/logo.svg" alt="Dataset Sample" />
            </div>
            <div class="dataset-section__result" ref="result"></div>
            <form
              action=""
              class="dataset-section__form form-dataset"
              v-on:submit.prevent="onSubmit"
              ref="datasetForm"
            >
              <div class="dataset-aside__description">
                Reqet a demo of Dataset get free consultatiion
              </div>
              <div class="form-dataset__row form-row">
                <input
                  type="email"
                  required
                  class="form-row__input form-row__input--email"
                  name="your_email"
                  id="your_email"
                  v-model="yourEmail"
                  placeholder="Email"
                />
              </div>
              <div class="form-dataset__row form-row">
                <button type="submit" class="form-row__submit" ref="submitBtn">
                  Request a dataset sample
                </button>
              </div>
            </form>
          </div>
        </div>
      </section>

      <section
        class="dataset-page__text dataset-text"
        v-for="text in dataset.page.texts"
        :key="`${text.title}_${text.title}`"
      >
        <div class="container dataset-text__container">
          <h3 class="dataset-text__title">
            {{ text.title }}
          </h3>
          <div class="dataset-text__text" v-html="text.inner"></div>
        </div>
      </section>

      <div class="dataset-page__text dataset-text">
        <div class="container dataset-text__container">
          <h3 class="dataset-text__title">Related Datasets</h3>
          <ul class="dataset-text__links dataset-text-links">
            <template v-for="service in Services">
              <li
                v-if="service.id !== dataset.id"
                :key="service.title"
                class="dataset-text-links__item"
              >
                <router-link
                  class="dataset-text-link"
                  :class="`dataset-text-link--${service.color}`"
                  :to="service.id"
                  >{{ service.link }}</router-link
                >
              </li>
            </template>
          </ul>
        </div>
      </div>
    </div>
  </MainLayout>
</template>

<script>
import MainLayout from "../layouts/MainLayout.vue";
import Services from "@/constants/services";

export default {
  components: {
    MainLayout,
  },
  mounted() {
    this.dataset = Services[this.$route.params.id];
    if (!this.dataset) this.$router.push("/");
  },
  updated() {
    this.dataset = Services[this.$route.params.id];
  },
  methods: {
    onSubmit: function () {
      console.log(this.yourEmail);

      this.$refs.datasetForm.remove();
      this.$refs.result.innerHTML = "Great! Check your Email!";
      this.$refs.result.classList.add("showed");
    },
  },
  data() {
    return {
      dataset: "",
      Services,
      yourEmail: "",
    };
  },
};
</script>

<style scoped lang="scss">
@import "../assets/styles/pages/dataset";
</style>
