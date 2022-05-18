<template>
  <MainLayout>
    <section class="hero-block">
      <div class="container hero-block__container">
        <div class="hero-block__text">
          <h1 class="hero-block__title">Get a dataset for your project</h1>
          <div class="hero-block__description">
            CleanDataSet is a commodities data provider for natural gas,
            electricity, weather, oil, and cryptocurrency. Our extensive data
            sets include nominations data for natural gas, as well as over
            35,000 locational marginal electricity prices. We are always seeking
            to expand our data collections and deliver the best experience for
            our customers. For each dataset, a free 30 day trial is available
            for your evaluation.
          </div>
          <router-link
            class="button button--stroked hero-block__button"
            to="/contact"
          >
            Request sample of dataset
          </router-link>
        </div>
        <div class="hero-block__image">
          <img
            src="../assets/images/homepage/hero-home.svg"
            alt="Dataset for your project"
          />
        </div>
      </div>
      <div class="container hero-block__partners">
        <img
          src="../assets/images/homepage/partner-1.png"
          srcset="../assets/images/homepage/partner-1_2x.png 2x"
          alt="partner 1"
          class="hero-block__partner"
        />
        <img
          src="../assets/images/homepage/partner-2.png"
          srcset="../assets/images/homepage/partner-2_2x.png 2x"
          alt="partner 2"
          class="hero-block__partner"
        />
        <img
          src="../assets/images/homepage/partner-3.png"
          srcset="../assets/images/homepage/partner-3_2x.png 2x"
          alt="partner 3"
          class="hero-block__partner"
        />
        <img
          src="../assets/images/homepage/partner-4.png"
          srcset="../assets/images/homepage/partner-4_2x.png 2x"
          alt="partner 4"
          class="hero-block__partner"
        />
        <img
          src="../assets/images/homepage/partner-1.png"
          srcset="../assets/images/homepage/partner-1_2x.png 2x"
          alt="partner 1"
          class="hero-block__partner"
        />
        <img
          src="../assets/images/homepage/partner-2.png"
          srcset="../assets/images/homepage/partner-2_2x.png 2x"
          alt="partner 2"
          class="hero-block__partner"
        />
        <img
          src="../assets/images/homepage/partner-3.png"
          srcset="../assets/images/homepage/partner-3_2x.png 2x"
          alt="partner 3"
          class="hero-block__partner"
        />
        <img
          src="../assets/images/homepage/partner-4.png"
          srcset="../assets/images/homepage/partner-4_2x.png 2x"
          alt="partner 4"
          class="hero-block__partner"
        />
      </div>
    </section>
    <section class="services-block">
      <div class="services-block__decor services-block-decor">
        <img
          src="../assets/images/homepage/decor-1.svg"
          alt="decor element"
          class="services-block-decor__item services-block-decor__item--1"
        />
        <img
          src="../assets/images/homepage/decor-2.svg"
          alt="decor element"
          class="services-block-decor__item services-block-decor__item--2"
        />
      </div>
      <div class="container services-block__container">
        <router-link
          class="services-block__item service"
          v-for="service in Services"
          :key="service.title"
          :to="{ name: 'dataset', params: { id: service.id } }"
        >
          <div class="service__icon">
            <img :src="service.imgUrl" :alt="service.title" />
          </div>
          <div class="service__title">
            {{ service.title }}
          </div>
          <div class="service__description" v-if="service.description">
            {{ service.description }}
          </div>
          <div
            class="service__list service-list"
            v-for="(list, index) in service.lists"
            :key="`${list.title}-${index}`"
          >
            <div class="service-list__title">
              {{ list.title }}
            </div>
            <ul
              class="service-list__items"
              v-if="list.items"
              :class="`service-list__items--${list.columns}`"
            >
              <li
                class="service-list__item"
                v-for="item in list.items"
                :key="item"
              >
                <span>
                  {{ item }}
                </span>
              </li>
            </ul>
          </div>
        </router-link>
        <div class="services-block__inner services-block-inner">
          <div class="services-block-inner__result" ref="result"></div>
          <form
            action=""
            class="services-block-inner__form form-services"
            v-on:submit.prevent="onSubmit"
            ref="subscribeForm"
          >
            <div class="form-services__title">
              Subscribe to the newsletter so as not to miss interesting news
            </div>
            <div class="form-services__description">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            </div>
            <div class="form-services__row form-row">
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
            <div class="form-services__row form-row">
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
            <div class="form-services__row form-row">
              <button type="submit" class="form-row__submit" ref="submitBtn">
                Subscribe
              </button>
            </div>
          </form>
        </div>
      </div>
    </section>
  </MainLayout>
</template>

<script>
import MainLayout from "../layouts/MainLayout.vue";
import Services from "../constants/services";
export default {
  components: {
    MainLayout,
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  unmounted() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    onSubmit: function () {
      console.log(this.yourName);
      console.log(this.yourEmail);

      this.$refs.subscribeForm.remove();
      this.$refs.result.innerHTML = "Great! Check your Email!";
      this.$refs.result.classList.add("showed");
    },
    handleScroll: function () {
      var vertical_position = 0;
      if (pageYOffset) vertical_position = pageYOffset;
      else if (document.documentElement.clientHeight)
        //ie
        vertical_position = document.documentElement.scrollTop;
      else if (document.body)
        //ie quirks
        vertical_position = document.body.scrollTop;
      var your_div = document.querySelector(".services-block-decor__item--1");
      var your_div_2 = document.querySelector(".services-block-decor__item--2");
      your_div.style.transform = `translateY(-${vertical_position / 10}px)`;
      your_div_2.style.transform = `translateY(${vertical_position / 6}px)`;
    },
  },
  data() {
    return {
      Services,
      yourName: "",
      yourEmail: "",
    };
  },
};
</script>

<style scoped lang="scss">
@import "../assets/styles/pages/home";
</style>
