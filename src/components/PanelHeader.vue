<template>
  <div>
    <p>Total de Confirmados: {{ data.last_available_confirmed }}</p>
    <p>
      Total de Óbitos: {{ data.last_available_deaths }}
      <small>{{ data.last_available_death_rate }}% dos habitantes</small>
    </p>
    <p>População estimada 2019: {{ data.estimated_population_2019 }}</p>
    <p>
      Casos confirmados por 100.000 habitantes:
      {{ data.last_available_confirmed_per_100k_inhabitants }}
    </p>
    <p>Última atualização: {{ data.last_available_date }}</p>
  </div>
</template>

<script>
export default {
  name: "PanelHeader",
  props: {
    data: {
      type: Object,
      required: true
    }
  }
};
</script>

<style lang="scss" scoped></style>
