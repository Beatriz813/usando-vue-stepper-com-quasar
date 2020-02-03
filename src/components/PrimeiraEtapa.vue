<template>
  <div class="row justify-center">
    <q-card class="col-8">
      <q-card-section class="q-gutter-sm">
        <q-input @input="continuar()" dense outlined label="Email" v-model="email"/>
        <q-input @input="continuar()" dense outlined label="Senha" type="password" v-model="senha"/>
        <q-input @input="continuar()" dense outlined label="Confirmar Senha" type="password" v-model="senhaConfirmacao"/>
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
export default {
  data () {
    return {
      email: '',
      senha: '',
      senhaConfirmacao: ''
    }
  },
  methods: {
    continuar () {
      if (this.email && this.senha && this.senhaConfirmacao) {
        this.$emit('can-continue', { value: true })
      }
    }
  }
}
</script>
