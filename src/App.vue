<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-img
          :src="require('@/assets/logo.svg')"
          alt="Covid19 Sumaré"
          class="shrink mr-2"
          contain
          transition="scale-transition"
          width="40"
        />

        <h1 class="title font-weight-regular">
          Covid19 Sumaré
        </h1>
      </div>
    </v-app-bar>

    <v-content>
      <PanelOverview />
    </v-content>
  </v-app>
</template>

<script>
import PanelOverview from './components/PanelOverview.vue';

export default {
  name: 'App',

  components: {
    PanelOverview
  }
};
</script>
