<template>
  <div class="row justify-center">
    <q-card class="col-8">
      <q-card-section>
        <q-input dense v-model="email" outlined label="Email" @input="finalizar()"/>
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
export default {
  data () {
    return {
      email: ''
    }
  },
  methods: {
    finalizar () {
      if (this.email) {
        this.$emit('can-continue', { value: true })
      }
    }
  }
}
</script>
