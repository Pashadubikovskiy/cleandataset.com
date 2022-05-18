<template>
  <div class="site">
    <SiteHeader class="site__header" />

    <slot></slot>

    <SiteFooter class="site__footer" />
  </div>
</template>

<script>
import SiteHeader from "../components/SiteHeader";
import SiteFooter from "../components/SiteFooter";
export default {
  components: {
    SiteHeader,
    SiteFooter,
  },
};
</script>

<style lang="scss">
@import "../assets/styles/scoped.scss";
</style>
