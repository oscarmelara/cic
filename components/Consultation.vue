/* eslint-disable no-unused-expressions */
<template>
  <section class="py-20 px-10 md:px-0">
    <div class="container mx-auto">
      <form class="w-full flex flex-wrap" enctype="multipart/form-data" @submit.prevent="submit()">
        <div class="w-full md:w-1/3 pr-0">
          <div class="w-full md:w-4/5 mx-auto">
            <div class="flex flex-col">
              <img class="w-16" src="~/assets/ic_info@2x.png" alt>
              <h4 class="text-lg color--blue font-bold mt-4">1. Datos personales</h4>
            </div>
            <div class="w-full mt-6">
              <label class="color--blue font-semibold text-sm" for>Primero coméntanos, eres:</label>
              <div class="mt-3">
                <div class="w-full">
                  <select
                    v-model="form.lead_type"
                    class="w-full border-b border-gray-500 text-sm py-3 outline-none rounded-none"
                  >
                    <option class="text-gray-200" disabled value>Seleccione un elemento</option>
                    <option value="paciente_familiar">Paciente o Familiar</option>
                    <option value="medico">Médico Referente</option>
                    <option value="institucion">Institución Referidora</option>
                  </select>
                </div>
              </div>
            </div>
            <div class="w-full mt-6">
              <input
                v-model="form.name"
                class="w-full border-b border-gray-500 text-sm py-3 outline-none rounded-none"
                placeholder="Nombre"
                type="text"
                required
              >
            </div>
            <div class="w-full mt-4">
              <input
                v-model="form.email"
                class="w-full border-b border-gray-500 text-sm py-3 outline-none rounded-none"
                placeholder="Correo electrónico"
                type="email"
                required
              >
            </div>
            <div class="w-full mt-4">
              <client-only placeholder>
                <vue-tel-input
                  v-model="form.tel"
                  v-bind="telProps"
                  @country-changed="countryChanged"
                />
              </client-only>
            </div>
          </div>
        </div>
        <div class="w-full md:w-1/3 pr-0 mt-12 md:mt-0">
          <div class="w-full md:w-4/5 mx-auto">
            <div class="flex flex-col">
              <img class="w-16" src="~/assets/ic_message@2x.png" alt>
              <h4 class="text-lg color--blue font-bold mt-4">2. Duda o consulta</h4>
            </div>

            <div class="w-full mt-5">
              <textarea
                v-model="form.consult"
                class="h-full w-full border-b border-gray-500 text-sm py-2 outline-none resize-none"
                cols="10"
                rows="12"
                placeholder="Consulta"
              />
            </div>
          </div>
        </div>
        <div class="w-full md:w-1/3 mt-12 md:mt-0">
          <div class="w-full md:w-4/5 mx-auto">
            <div class="flex flex-col">
              <img class="w-16" src="~/assets/ic_exams@2x.png" alt>
              <h4 class="text-lg color--blue font-bold mt-4">3. Exámenes clínicos previos</h4>
            </div>
            <div class="w-full">
              <div class="w-full h-32 overflow-y-auto mt-6">
                <p
                  v-for="(image, index) in imagenes"
                  :key="index"
                  class="text-sm color--sky flex items-center justify-start"
                >
                  <img class="w-10" src="~/assets/ic_attach@2x.png" alt>
                  {{ image.name }}
                </p>
              </div>
              <label
                class="text-sm color--blue font-semibold bg-white px-6 py-2 block rounded-lg text-center border border-blue-800 cursor-pointer mt-2"
                for="send"
              >Subir archivos</label>
              <input
                id="send"
                ref="file"
                type="file"
                multiple="multiple"
                class="mt-2 hidden"
                @change="selectedFile()"
              >
            </div>
            <div class="w-full mt-4">
              <label
                class="color--blue font-semibold text-sm"
                for
              >¿Tiene resultados de exámenes en la nube?</label>
              <input
                v-model="form.url"
                type="text"
                class="w-full border-b border-gray-500 text-sm py-3 outline-none rounded-none"
                placeholder="Comparte tu enlace aquí"
              >
            </div>
            <div class="flex justify-end items-center mt-6">
              <img v-if="wait === true" class="w-20" src="~/assets/spinner.gif" alt>
              <button
                class="px-10 py-3 text-sm font-semibold rounded-lg btn--sky text-white outline-none hover:opacity-75"
              >Enviar</button>
            </div>
          </div>
        </div>
      </form>
    </div>
  </section>
</template>
<script>
import axios from '~/plugins/axios'

export default {
  data: () => {
    return {
      API_BASE_URL: process.env.API_BASE_URL,
      imgSelected: [],
      pdfSelected: [],
      zipSelected: [],
      imagenes: [],
      succesMessage: false,
      errorMessage: false,
      wait: false,
      country: null,
      telProps: {
        enabledCountryCode: false,
        onlyCountries: [
          'CA',
          'US',
          'MX',
          'BZ',
          'GT',
          'SV',
          'HN',
          'NI',
          'CR',
          'PA',
          'VE',
          'CO',
          'BO',
          'BR',
          'EC',
          'PE',
          'UY',
          'PY',
          'CL'
        ],
        inputOptions: {
          showDialCode: true
        }
      },
      form: {
        lead_type: '',
        name: '',
        email: '',
        tel: '',
        consult: '',
        file: [],
        url: ''
      }
    }
  },
  methods: {
    countryChanged (country) {
      this.country = '+' + country.dialCode
    },
    selectedFile () {
      if (this.imagenes === '') {
        this.imagenes = this.$refs.file.files
      } else {
        for (let i = 0; i < this.$refs.file.files.length; i++) {
          const file = this.$refs.file.files[i]
          this.imagenes.push(file)
        }
      }
    },
    submit () {
      this.wait = true
      const formData = new FormData()
      for (let i = 0; i < this.imagenes.length; i++) {
        const file = this.imagenes[i]
        formData.append('files[' + i + ']', file)
      }
      formData.set('lead_type', this.form.lead_type)
      formData.set('name', this.form.name)
      formData.set('email', this.form.email)
      formData.set('tel', this.form.tel)
      formData.set('consult', this.form.consult)
      formData.set('url', this.form.url)
      axios
        .post(
          'https://centrointernacionaldecancer.com/app/api/updateMedia',
          formData,
          {
            headers: {
              'Content-Type': 'multipart/form-data'
            }
          }
        )
        .then((response) => {
          this.$swal(
            'Exito',
            'Tus datos han sido enviados con éxito.',
            'success'
          )
          this.wait = false
          this.clear()
        })
        .catch(() => {
          this.$swal('Oops...', 'Hubo un error, intenta más tarde.', 'error')
          this.wait = false
          this.clear()
        })
    },
    clear () {
      this.form.lead_type = ''
      this.form.name = ''
      this.form.email = ''
      this.form.tel = ''
      this.form.consult = ''
      this.form.url = ''
      this.imagenes = []
    }
  }
}
</script>
<style lang="scss">
.new-button {
  display: inline-block;
  padding: 8px 8px;
  cursor: pointer;
  border-radius: 25px;
  font-size: 12px;
  color: #fff;
}
.vue-tel-input {
  border: 0 !important;
  outline: none !important;
  input {
    border-bottom: 1px solid rgba(160, 174, 192, 0.8) !important;
    padding-top: 0.75rem !important;
    padding-bottom: 0.75rem !important;
    border-radius: 0;
  }
  &:focus-within {
    box-shadow: none;
  }
}
</style>
