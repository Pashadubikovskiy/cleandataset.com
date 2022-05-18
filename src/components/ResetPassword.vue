<template>
  <form
    class="hero-block-inner__form form-account form-account--reset"
    v-on:submit.prevent="onSubmit"
  >
    <div class="form-account__title">Password reset</div>
    <div class="form-account__row form-row">
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
    <div class="form-account__links form-row">
      <router-link
        class="form-row__link form-row__link--button"
        to="/account/sign-in"
      >
        Back to Sign in page
      </router-link>
      <button type="submit" class="form-row__submit form-row__submit--parted">
        Reset
      </button>
    </div>
  </form>
  <div class="result">
    <div class="result__image">
      <img
        src="../assets/images/letter.svg"
        alt="An email with recovery link has been sent to your email"
      />
    </div>
    <div class="result__title">
      An email with recovery link has been sent to your email
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      yourEmail: "",
    };
  },
  methods: {
    onSubmit: function () {
      console.log(this.yourEmail);
      document
        .querySelectorAll(".hero-block-inner__image, .form-account")
        .forEach((el) => el.classList.add("hidden"));
      document.querySelector(".result").classList.add("visible");
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/styles/pages/account";
</style>
