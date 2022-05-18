<template>
  <form
    class="hero-block-inner__form form-account"
    v-on:submit.prevent="onSubmit"
  >
    <div class="form-account__title">Sign Up</div>
    <div class="form-account__row form-row">
      <input
        type="text"
        required
        class="form-row__input form-row__input--name"
        name="your_name"
        id="your_name"
        v-model="yourName"
        placeholder="Name"
      />
    </div>
    <div class="form-account__row form-row">
      <input
        type="text"
        required
        class="form-row__input form-row__input--name"
        name="your_lastname"
        id="your_lastname"
        v-model="yourLastname"
        placeholder="Lastname"
      />
    </div>
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
    <div class="form-account__row form-row">
      <input
        type="password"
        ref="password"
        required
        class="form-row__input form-row__input--password"
        name="your_password"
        id="your_password"
        v-model="yourPassword"
        placeholder="Password"
      />
      <button @click="changeType" type="button" class="form-account__eye">
        <svg
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          :class="!showPassword ? 'form-account__eye--active' : ''"
        >
          <path
            d="M10.5 10.677a2 2 0 0 0 2.823 2.823M3 3l18 18L3 3Z"
            stroke="#E5E5E5"
            stroke-width="1.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <path
            d="M12 6c4.008 0 6.701 3.158 9 6-.33.52-.69 1.022-1.078 1.5M7.362 7.561C5.68 8.74 4.279 10.42 3 12c1.889 2.991 5.282 6 9 6 1.55 0 3.043-.523 4.395-1.35L7.362 7.561Z"
            stroke="#E5E5E5"
            stroke-width="1.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          stroke-width="1.5"
          fill="none"
          viewBox="0 0 24 24"
          :class="showPassword ? 'form-account__eye--active' : ''"
        >
          <path
            d="M12 14a2 2 0 1 0 0-4 2 2 0 0 0 0 4Z"
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <path
            d="M21 12c-1.889 2.991-5.282 6-9 6s-7.111-3.009-9-6c2.299-2.842 4.992-6 9-6s6.701 3.158 9 6Z"
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </button>
    </div>
    <div class="form-account__row form-row">
      <input
        type="password"
        ref="password2"
        required
        class="form-row__input form-row__input--password"
        name="your_password"
        id="your_password"
        v-model="confirmPassword"
        placeholder="Confirm password"
      />
      <button @click="changeType" type="button" class="form-account__eye">
        <svg
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          :class="!showPassword ? 'form-account__eye--active' : ''"
        >
          <path
            d="M10.5 10.677a2 2 0 0 0 2.823 2.823M3 3l18 18L3 3Z"
            stroke="#E5E5E5"
            stroke-width="1.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <path
            d="M12 6c4.008 0 6.701 3.158 9 6-.33.52-.69 1.022-1.078 1.5M7.362 7.561C5.68 8.74 4.279 10.42 3 12c1.889 2.991 5.282 6 9 6 1.55 0 3.043-.523 4.395-1.35L7.362 7.561Z"
            stroke="#E5E5E5"
            stroke-width="1.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          stroke-width="1.5"
          fill="none"
          viewBox="0 0 24 24"
          :class="showPassword ? 'form-account__eye--active' : ''"
        >
          <path
            d="M12 14a2 2 0 1 0 0-4 2 2 0 0 0 0 4Z"
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <path
            d="M21 12c-1.889 2.991-5.282 6-9 6s-7.111-3.009-9-6c2.299-2.842 4.992-6 9-6s6.701 3.158 9 6Z"
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </button>
    </div>
    <div class="form-account__row form-row">
      <button type="submit" class="form-row__submit">Sign up</button>
    </div>
    <div class="form-account__text">
      Already have an account?
      <router-link class="form-account__link" to="/account/sign-in"
        >Sign in</router-link
      >
      or
      <router-link class="form-account__link" to="/account/reset-password"
        >Reset password</router-link
      >
    </div>
  </form>
  <div class="result">
    <div class="result__image">
      <img
        src="../assets/images/letter.svg"
        alt="An email with recovery link has been sent to your email"
      />
    </div>
    <div class="result__title">Signup link has been sent to your email</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      yourName: "",
      yourLastname: "",
      yourEmail: "",
      yourPassword: "",
      confirmPassword: "",
      showPassword: false,
    };
  },
  methods: {
    validatePassword: function () {
      if (this.yourPassword !== this.confirmPassword) {
        this.$refs.password2.classList.add("error");

        return false;
      } else {
        return true;
      }
    },
    onSubmit: function () {
      console.log(this.validatePassword);
      if (this.validatePassword()) {
        console.log(this.yourName);
        console.log(this.yourLastname);
        console.log(this.yourEmail);
        console.log(this.yourPassword);

        document
          .querySelectorAll(".hero-block-inner__image, .form-account")
          .forEach((el) => el.classList.add("hidden"));
        document.querySelector(".result").classList.add("visible");
      }
    },
    changeType: function () {
      this.showPassword = !this.showPassword;

      if (!this.showPassword) {
        this.$refs.password.type = "password";
        this.$refs.password2.type = "password";
      } else {
        this.$refs.password.type = "text";
        this.$refs.password2.type = "text";
      }
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/styles/pages/account";
</style>
