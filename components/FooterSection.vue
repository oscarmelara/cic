<template>
  <div>
    <footer class="w-full footer py-16">
      <div class=" container mx-auto md:px-10 lg:px-10">
        <div class="w-full flex flex-wrap">
          <div class="w-full md:w-1/2 lg:w-1/4">
            <img class="w-48 mx-auto" src="~/assets/ic_footer_logo@2x.png" alt="">
          </div>
          <div class="w-full md:w-1/2 lg:w-1/4 mt-10 md:mt-0">
            <p class="color--sky text-base text-center md:text-left">Links de interés</p>
            <ul class="mt-6 flex items-center md:items-start flex-col">
              <a class="mt-5 block text-white text-sm" href="http://www.centrodecancer.com.sv/es/" target="_blank">Centro Internacional Del Cáncer</a>
              <a class="mt-5 block text-white text-sm" href="http://radiocirugiarobotica.com/" target="_blank">Centro de Radiocirugía Robótica </a>
            </ul>
          </div>
          <div class="w-full md:w-1/2 px-10 lg:w-1/4 md:px-0 mt-10 lg:mt-0">
            <p class="color--sky text-base text-center md:text-left">Contáctenos</p>
            <div class="flex mt-6">
              <div class="w-1/12 mr-3 flex justify-center items-center">
                <img class="w-4" src="~/assets/ic_location@2x.png" alt="">
              </div>
              <div class="w-4/5">
                <p class="text-sm text-white">3ra Calle Poniente, Block No 122, Colonia Escalón, Zona 11, San Salvador, El Salvador</p>
              </div>
            </div>
            <div class="flex mt-5">
              <div class="w-1/12 mr-3 flex justify-center items-center">
                <img class="w-4" src="~/assets/ic_telephone@2x.png" alt="">
              </div>
              <div class="w-4/5">
                <p class="text-sm text-white">(503) 2506-2001</p>
              </div>
            </div>
            <div class="flex mt-5">
              <div class="w-1/12 mr-3 flex justify-center items-center">
                <img class="w-4" src="~/assets/ic_mail@2x.png" alt="">
              </div>
              <div class="w-4/5">
                <p class="text-sm text-white">info@centrodecancer.com.sv</p>
              </div>
            </div>
            <div class="flex mt-5">
              <div class="w-1/12 mr-3 flex justify-center items-center">
                <img class="w-4" src="~/assets/ic_hours@2x.png" alt="">
              </div>
              <div class="w-4/5">
                <p class="text-sm text-white">De lunes a viernes <br> 8:00 a.m. a 6:00 p.m.</p>
              </div>
            </div>
          </div>
          <div class="w-full md:w-1/2 lg:w-1/4 mt-10 lg:mt-0 flex flex-col items-center md:items-start">
            <p class="color--sky text-base text-center md:text-left">Redes sociales</p>
            <ul class="flex justify-start items-start max-w-sm mt-6">
              <li><a href="https://www.facebook.com/CentroInternacionaldeCancer/" target="_blank"><img class="w-10 mr-4" src="~/assets/ic_facebook@2x.png" alt=""></a></li>
              <li><a href="https://twitter.com/cdecancer" target="_blank"><img class="w-10 mr-4" src="~/assets/ic_twitter@2x.png" alt=""></a></li>
              <li><a href="https://www.youtube.com/user/centrodecancersv" target="_blank"><img class="w-10" src="~/assets/ic_youtube.png" alt=""></a></li>
            </ul>
          </div>
        </div>
      </div>

    </footer>
    <div class=" footer w-full flex justify-center items-center py-4">
      <p class=" text-sm text-white font-normal tracking-normal text-center">Derechos Reservados 2020 | Centro Internacional del Cáncer</p>
    </div>
  </div>
</template>
<script>
export default {}
</script>
<style lang="scss" scoped>
.footer {
  background-color: #00122b;
}
</style>
