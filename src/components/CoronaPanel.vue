<template>
  <div>
    <ul>
      <li v-for="data in panelData" :key="data.order_for_place">
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
        <hr />
        <p>Data: {{ data.last_available_date }}</p>
        <p>Semana epidemiológica: {{ data.epidemiological_week }}</p>
        <p>Dias à partir do primeiro caso: {{ data.order_for_place }}</p>
        <p>Óbitos no dia': {{ data.new_deaths }}</p>
        <p>Novos confirmados: {{ data.new_confirmed }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "CoronaPanel",
  data() {
    return {
      panelData: null
    };
  },
  created() {
    axios
      .get(
        "https://brasil.io/api/dataset/covid19/caso_full/data?search=&state=SP&city=Sumaré"
      )
      .then(response => {
        this.panelData = response.data.results;
      });
  }
};
</script>

<style scoped lang="scss"></style>
