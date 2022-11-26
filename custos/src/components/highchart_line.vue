<template>
    <VueHighcharts
        type="chart"
        :options="chartOptions"
        :redrawOnUpdate="true"
        :oneToOneUpdate="false"
        :animateOnUpdate="true" />
</template>
<script setup lang="ts">
import VueHighcharts from 'vue3-highcharts';
import { computed } from 'vue';

const props = defineProps({
  categories: {
    type: Array,
  },
  dataset: {
    type: Array,
  },
  height: {
    type: Number,
    required: false,
    default: 150,
  },
  title: {
    type: String,
    required: false,
  },
  xAxis: {
    type: Object,
    required: false,
  },
  yAxis: {
    type: Object,
    required: false,
  },
  width: {
    type: Number,
    required: false,
    default: 200,
  },
});

const chartOptions = computed(() => ({
  chart: {
    type: 'line',
    height: props.height,
    width: props.width,
  },
  credits: {
    enabled: false,
  },
  legend: {
    enabled: false,
    layout: 'vertical',
    align: 'right',
    verticalAlign: 'middle',
  },
  title: {
    enabled: props.title != null,
    text: props.title,
  },
  xAxis: {
    title: {
      enabled: props.xAxis != null && props.xAxis.title != null,
      text: props.xAxis?.title,
    },
    categories: props.categories,
  },
  yAxis: {
    title: {
      enabled: props.yAxis != null && props.yAxis.title != null,
      text: props.yAxis?.title,
    },
  },
  series: props.dataset,
}));
</script>
