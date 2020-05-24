<template>
  <div>
    <PanelHeader v-if="panelData" :data="panelData[0]" />
    <PanelList v-if="panelData" :data="panelData" />
  </div>
</template>

<script>
import PanelHeader from '@/components/PanelHeader.vue';
import PanelList from '@/components/PanelList.vue';
import axios from 'axios';

export default {
  name: 'CoronaPanel',
  components: {
    PanelHeader,
    PanelList
  },
  data() {
    return {
      panelData: null
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      axios
        .get(
          'https://brasil.io/api/dataset/covid19/caso_full/data?search=&state=SP&city=Sumaré'
        )
        .then(response => {
          this.panelData = response.data.results;
        });
    }
  }
};
</script>

<style scoped lang="scss"></style>
