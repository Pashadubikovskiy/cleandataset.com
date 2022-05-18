<template>
  <form
    class="hero-block-inner__form form-account"
    v-on:submit.prevent="onSubmit"
  >
    <div class="form-account__title">Sign In</div>
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
      <button type="submit" class="form-row__submit">Login</button>
    </div>
    <div class="form-account__links">
      <router-link class="form-account__link" to="/account/reset-password"
        >Reset password</router-link
      >
      <router-link class="form-account__link" to="/account/sign-up"
        >Sign up now</router-link
      >
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      yourEmail: "",
      yourPassword: "",
      showPassword: false,
    };
  },
  methods: {
    onSubmit: function () {
      console.log(this.yourEmail);
      console.log(this.yourPassword);
    },
    changeType: function () {
      this.showPassword = !this.showPassword;

      if (!this.showPassword) {
        this.$refs.password.type = "password";
      } else {
        this.$refs.password.type = "text";
      }
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/styles/pages/account";
</style>
