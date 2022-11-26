<template>
  <q-page class="q-pa-xs">
    <q-card class="">
      <q-card-section class="full-width">
        Receitas
      </q-card-section>
      <q-card-section horizontal>
        <q-card-section class="full-width">
        R$ 99.999,00
        </q-card-section>
        <q-card-section class="q-pa-none">
          <HighchartLine :height="100" :width="250" :dataset="dataset" :categories="categories" />
        </q-card-section>
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script setup lang="ts">
import HighchartLine from 'src/components/highchart_line.vue';
import { ref } from 'vue';

const dataset = [{
  // name: 'New project stars',
  data: [25, 39, 30, 15, 39, 30],
}];

const categories = ['J', 'J', 'A', 'S', 'O', 'N'];

</script>
