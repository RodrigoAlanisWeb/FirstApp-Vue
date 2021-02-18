<template>
  <div>
    <h2>Tipo de Cuenta: {{ cuenta }}</h2>
    <h2>Saldo: {{ saldo }}</h2>
    <h2 v-if="state">Cuenta Activa</h2>
    <h2 v-else>Cuenta Inactiva</h2>
    <ul>
      <li v-for="(service, index) in services" :key="index">
        {{ index + 1 }} : {{ service }}
      </li>
    </ul>
    <AccionSaldo texto="true" @accion="aumentar"/>
    <AccionSaldo :saldo="saldo" texto="false" @accion="disminuir"/>
    <div v-if="saldo === 0" class="alert alert-danger">
          El Saldo A Llegado A Cero
      </div>
  </div>
</template>

<script>
import AccionSaldo from "./AccionSaldo";

export default {
  name: "Cuenta",
  data() {
    return {
      saldo: 1000,
      cuenta: "Visa",
      state: true,
      services: ["giro", "abono", "transferencia", "saldo"],
    };
  },
  components: {
    AccionSaldo,
  },
  methods: {
    aumentar() {
      this.saldo += 100;
    },
    disminuir() {
      this.saldo -= 100;
    },
  },
};
</script>

<style scoped>
li {
  list-style: none;
}
</style>