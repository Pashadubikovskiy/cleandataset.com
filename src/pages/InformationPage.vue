<template>
  <MainLayout>
    <section class="page-hero">
      <div class="page-hero__background">
        <img
          src="../assets/images/information.jpg"
          srcset="../assets/images/information_2x.jpg 2x"
          alt="Legal Information"
          class="page-hero__image"
        />
      </div>
      <div class="container page-hero__container">
        <div class="page-hero__text">
          <h1 class="page-hero__title">Legal Information</h1>
          <div class="page-hero__description">
            <img
              src="../assets/images/icons/icon-calendar.svg"
              alt="Legal Information"
            />
            Last Update: 2020 Jan 22
          </div>
        </div>
      </div>
    </section>
    <section class="page-content">
      <div class="page-content__container">
        <div class="page-content__intro">
          PLEASE READ THIS PRIVACY POLICY CAREFULLY BEFORE USING THIS WEBSITE OR
          SUBMITTING ANY PERSONAL INFORMATION. BY USING THIS WEBSITE YOU ARE
          AGREEING TO THESE PRIVACY TERMS and TERMS OF SERVICE (“TOS”). IF YOU
          DO NOT AGREE, DO NOT USE THIS WEBSITE.
        </div>
        <div class="page-content__subtitle">Commitment to Privacy</div>
        <div class="page-content__text">
          This Website, www.cleandataset.com, (the "Website") is owned and
          operated by CleanDataSet, Inc. ("CDS", "us", "we" or "our"), a
          Delaware corporation. CDS respects the privacy of every individual who
          uses this Website and therefore, we only wish to process and use the
          data obtained through the Website for our own purposes. The privacy
          policy located on this Website ("Privacy Policy") outlines the
          information we will collect and how we will use that information.
        </div>
        <div class="page-content__subtitle">Changes to Privacy Statement</div>
        <div class="page-content__text">
          Because of changes in Internet technology and practices, this Privacy
          Policy, and our security and other policies may change from time to
          time. Please consult this portion of the Website for important changes
          to the Privacy Policy as they occur. Unless otherwise provided in an
          agreement between you and CDS, by using the Website after CDS posts
          any changes to this Privacy Policy, you agree to accept those changes,
          whether or not you have reviewed them, and such acceptance shall be
          deemed legally conclusive. If at any time you choose not to accept the
          terms of this Privacy Policy, you should not use the Website and enter
          information about yourself or your business.
        </div>
        <div class="page-content__subtitle">Other Agreements with CDS</div>
        <div class="page-content__text">
          For users who have entered into agreements with CDS for other services
          off-line, those agreements shall govern the relationship between the
          user and CDS for that service. To the extent those provisions differ
          from this Privacy Policy, the terms of that agreement shall govern and
          control that particular service.
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
@import "../assets/styles/pages/textpage";
</style>
