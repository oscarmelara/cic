<template>
  <div>
    <nuxt />
    <FooterSection />
  </div>
</template>

<script>
import FooterSection from '~/components/FooterSection.vue'

export default {
  components: {
    FooterSection
  }
}
</script>
>

<style lang="scss">

html {
  font-family: "Spartan", sans-serif!important;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  button {
    outline: none!important;
  }
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.color--sky {
  color: #68cbe5;
}
.color--blue {
  color: #073370;
}
.btn--sky {
  background-color: #68cbe5;
}
</style>
