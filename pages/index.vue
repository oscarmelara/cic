<template>
  <div>
    <Header />
    <Process />
    <TextDivisor />
    <Consultation />
    <Information />
  </div>
</template>

<script>
import Header from '~/components/Header.vue'
import Process from '~/components/Process.vue'
import TextDivisor from '~/components/TextDivisor.vue'
import Consultation from '~/components/Consultation.vue'
import Information from '~/components/Information.vue'

export default {
  components: {
    Header,
    Process,
    TextDivisor,
    Consultation,
    Information
  }
}
</script>
