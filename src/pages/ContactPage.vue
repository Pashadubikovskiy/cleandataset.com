<template>
  <MainLayout>
    <section class="hero-block">
      <div class="container hero-block__container">
        <div class="hero-block__text">
          <h1 class="hero-block__title">Contact us</h1>
          <div class="hero-block__description">
            If you have a question about our features, datasets, usage, or want
            a demo, or anything else, our team is ready to help.
          </div>
        </div>
        <div class="hero-block__inner hero-block-inner">
          <div class="hero-block-inner__image">
            <img
              src="../assets/images/circle.svg"
              alt="Dataset for your project"
            />
          </div>
          <form
            class="hero-block-inner__form form-contact"
            v-on:submit.prevent="onSubmit"
          >
            <div class="form-contact__row form-row">
              <input
                type="text"
                required
                class="form-row__input form-row__input--name"
                name="your_name"
                id="yourName"
                v-model="yourName"
                placeholder="Name"
              />
            </div>
            <div class="form-contact__row form-row">
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
            <div class="form-contact__row form-row">
              <textarea
                rows="3"
                class="form-row__textarea form-row__textarea--message"
                name="your_message"
                id="your_message"
                v-model="yourMessage"
                placeholder="Message"
              >
              </textarea>
            </div>
            <div class="form-contact__row form-row">
              <button type="submit" class="form-row__submit">Send</button>
            </div>
          </form>
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
  methods: {
    onSubmit: function () {
      console.log(this.yourName);
      console.log(this.yourEmail);
      console.log(this.yourMessage);
    },
  },
  data() {
    return {
      yourName: "",
      yourEmail: "",
      yourMessage: "",
    };
  },
};
</script>

<style scoped lang="scss">
@import "../assets/styles/pages/contact";
</style>
