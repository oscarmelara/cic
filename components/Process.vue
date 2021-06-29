<template>
  <section id="process" class="process h-full relative pt-24 md:pt-12 md:pb-56 pb-0  px-10 md:px-0">
    <!-- <div class="container h-full mx-auto flex flex-wrap md:px-10 lg:px-10">
      <div class="w-full">
        <h4 class="text-center text-white text-2xl md:text-3xl font-bold leading-tight">
          Conoce nuestro proceso
        </h4>
      </div>
      <div class="w-full flex flex-wrap mt-10">
        <div class="w-full md:w-1/2 md:pr-4 relative">
          <div
            class="w-full process-one bg-cover bg-center bg-no-repeat flex items-end "
          >
            <div class="overlay absolute w-full h-full"/>
            <div class=" flex flex-col md:pl-10 md:pb-10 pl-6 pb-6">
              <img
                class="z-10 w-10 md:w-16"
                src="~/assets/ic_national@2x.png"
                alt=""
              >
              <h4 class="z-10 text-white text-2xl md:text-3xl font-bold mt-4">
                Paciente <br>
                Nacional
              </h4>
            </div>
          </div>
        </div>
        <div class="w-full md:w-1/2 md:pl-4 relative mt-6 md:mt-0">
          <div
            class="w-full process-two bg-cover bg-center bg-no-repeat flex items-end"
          >
            <div class="overlay absolute w-full h-full"/>
            <div class="flex flex-col md:pl-10 md:pb-10 pl-6 pb-6">
              <img
                class=" z-10 w-10 md:w-16"
                src="~/assets/ic_international@2x.png"
                alt=""
              >
              <h4 class="z-10 text-white text-2xl md:text-3xl font-bold">
                Paciente <br>
                Internacional
              </h4>
            </div>
          </div>
        </div>
      </div>
    </div> -->
    <img class="divider" src="~/assets/divisor.png" alt="">
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss">
.process {
    background-color: #073370;
  .process-one {
    background-image: url("~assets/img_national@2x.png");
    border-radius: 32px;
    height: 350px;
  }
  .process-two {
    background-image: url("~assets/img_international@2x.png");
    border-radius: 32px;
    height: 350px;
  }
}
.overlay {
  background: linear-gradient(0deg, #073370 0.1%, transparent 100%);
  border-radius: 32px;
  z-index: 1;
}
.divider {
    position: absolute;
    bottom: -1px;
    left: 0;
    right: 0;
    width: 100%;
    height: auto;
}
</style>
