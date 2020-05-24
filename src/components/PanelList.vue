<template>
  <v-data-table
    :headers="headers"
    :items="data"
    :items-per-page="10"
    disable-sort
  >
    <template v-slot:item.new_confirmed="{ item }">
      <v-chip :color="getConfirmedColor(item.new_confirmed)">
        {{ item.new_confirmed }}
      </v-chip>
    </template>

    <template v-slot:item.new_deaths="{ item }">
      <v-chip :color="getDeathsColor(item.new_deaths)">
        {{ item.new_deaths }}
      </v-chip>
    </template>
  </v-data-table>
</template>

<script>
export default {
  name: 'PanelList',
  props: {
    data: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      headers: [
        {
          text: 'Data',
          align: 'start',
          sortable: false,
          value: 'last_available_date'
        },
        { text: 'Casos confirmados', value: 'new_confirmed' },
        { text: 'Óbitos', value: 'new_deaths' },
        { text: 'Semana epidemiológica', value: 'epidemiological_week' },
        { text: 'Dias à partir do 1º caso', value: 'order_for_place' }
      ]
    };
  },
  methods: {
    getConfirmedColor(value) {
      return value > 0 ? 'green lighten-3' : 'green lighten-5';
    },
    getDeathsColor(value) {
      return value > 0 ? 'red lighten-3' : 'red lighten-5';
    }
  }
};
</script>

<style lang="scss" scoped></style>
