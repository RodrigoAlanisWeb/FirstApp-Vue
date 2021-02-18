<template>
  <div>
      <button v-if="texto === 'true'" @click="accion" class="btn btn-success m-3">
          Aumentar Saldo
      </button>
      <button :disabled="saldo === 0" v-else @click="accion" class="btn btn-danger m-3">
          Disminuir Saldo
      </button>
  </div>
</template>

<script>
export default {
    name: 'AccionSaldo',
    props: {
        texto: String,
        saldo: Number
    },
    methods: {
        accion() {
            this.$emit('accion')
        }
    }
}
</script>

<style>

</style>