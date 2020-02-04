<template>
  <q-page class="container">
    <horizontal-stepper
      :steps="etapas"
      @completed-step="etapaCompleta"
      @active-step="etapaAtiva"
      @stepper-finished="etapaFinalizada"></horizontal-stepper>
  </q-page>
</template>

<script>
import HorizontalStepper from 'vue-stepper'
import PrimeiraEtapa from 'components/PrimeiraEtapa.vue'
import SegundaEtapa from 'components/SegundaEtapa.vue'
export default {
  name: 'PageIndex',
  components: {
    HorizontalStepper
  },
  data () {
    return {
      etapas: [
        { icon: 'email', name: 'first', title: 'Primeira Etapa', component: PrimeiraEtapa, completed: false },
        { icon: 'email', name: 'second', title: 'Segunda Etapa', component: SegundaEtapa, completed: false }
      ]
    }
  },
  methods: {
    etapaCompleta (payload) {
      console.log('Etapa Completa => ', payload)
    },
    etapaAtiva (payload) {
      console.log('Etapa Ativa => ', payload)
    },
    etapaFinalizada (payload) {
      console.log('Etapa Finalizada => ', payload)
    }
  }
}
</script>
