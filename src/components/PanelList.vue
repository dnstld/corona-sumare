<template>
  <ul>
    <li v-for="value in data" :key="value.order_for_place">
      <p>Data: {{ value.last_available_date }}</p>
      <p>Semana epidemiológica: {{ value.epidemiological_week }}</p>
      <p>Dias à partir do primeiro caso: {{ value.order_for_place }}</p>
      <p>Óbitos no dia: {{ value.new_deaths }}</p>
      <p>Novos confirmados: {{ value.new_confirmed }}</p>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'PanelList',
  props: {
    data: {
      type: Array,
      required: true
    }
  }
};
</script>

<style lang="scss" scoped></style>
