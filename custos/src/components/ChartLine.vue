<template>
    <VueHighcharts 
        type="chart"
        :options="chartData"
        :redrawOnUpdate="true"
        :oneToOneUpdate="false"
        :animateOnUpdate="true"
        @rendered="onRender"
        @update="onUpdate"
        @destroy="onDestroy"
    />
</template>
<script setup>
import { computed, ref } from 'vue';

import VueHighcharts from 'vue3-highcharts';

import HighchartsMore from 'highcharts/highcharts-more'
import Highcharts from 'highcharts'

HighchartsMore(Highcharts)

const data = ref(Array.from({length: 6}, () => Math.floor(Math.random() * 100000)))
const chartData = computed(() =>{
    return {
        chart: {
            height: 200
        },

        title: {
            text: 'Resultado YTD'
        },

        yAxis: {
            title: {
                enabled: false,
            }
        },

        xAxis: {
            accessibility: {
                rangeDescription: 'Range: 2021-01-01 to 2022-12-31'
            }
        },

        legend: {
            enabled: false,
        },

        credits: {
            enabled: false,
        },

        plotOptions: {
            series: {
                label: {
                    connectorAllowed: false
                },
                pointStart: 2010
            }
        },

        series: [{
            name: 'Receitas',
            data: Array.from({length: 12}, () => Math.floor(Math.random() * 1000000))
        }, {
            name: 'Despesas',
            data: Array.from({length: 12}, () => Math.floor(Math.random() * 1000000))
        }, {
            name: 'Resultados',
            data: Array.from({length: 12}, () => Math.floor(Math.random() * 1000000))
        }],
    }
});

const onRender = () => {
    console.log('Chart rendered');
};

const onUpdate = () => {
    console.log('Chart updated');
};

const onDestroy = () => {
    console.log('Chart destroyed');
};

</script>
<style>
.vue-highcharts {
  width: 100%;
}
</style>
