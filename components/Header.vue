<template>
  <section class="header bg-cover bg-center bg-no-repeat pt-0 px-10 md:px-0">
    <div class="container h-full mx-auto flex flex-col">
      <div class="w-full mx-auto mt-16 md:mt-24">
        <img class="w-48 md:w-1/4 mx-auto" src="~/assets/ic_logo@2x.png" alt>
      </div>
      <div class="w-full mt-24 md:mt-32">
        <div>
          <h1 class="text-white font-medium text-center">Consulta en línea,</h1>
          <h4
            class="text-center font-bold text-white text-lg md:text-3xl leading-tight"
          >con los mejores especialistas de la región.</h4>
          <p
            class="text-center max-w-md font-semibold text-sm md:text-base text-white mx-auto color--sky leading-normal tracking-wide mt-6"
          >
            Nacimos para cuidar de su salud ofreciendo tratamientos para el
            cáncer y enfermedades neurológicas complejas.
          </p>
        </div>
      </div>
      <div class="w-full mt-32 md:mt-56 mb-32">
        <img
          v-scroll-to="'#process'"
          class="mx-auto cursor-pointer"
          src="~/assets/ic_arrow@2x.png"
          alt
        >
      </div>
    </div>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.header {
  background-image: url("~assets/background_section_1@2x.png");
  h1 {
    font-size: 5rem;
  }

  @media (max-width: 512px) {
    h1 {
      font-size: 1.75rem;
    }
  }
}
</style>
