<template>
    <va-card color="background-element">
        <div class="row">
            <div class="flex md6 xs6" style="padding: 0.75rem;">
                <va-card color="Danger">
                    <va-card-content>
                        <p style="font-weight: 700;" class="display-2">-1°C</p>
                        <p class="display-2">Текущая температура</p>
                    </va-card-content>
                </va-card>
            </div>
            <div class="flex md6 xs6" style="padding: 0.75rem;">
                <va-card color="Success">
                    <va-card-content>
                        <p style="font-weight: 700;" class="display-2">50%</p>
                        <p class="display-2">Текущая влажность</p>
                    </va-card-content>
                </va-card>
            </div>
        </div>
        <div class="row">
            <div class="flex md12 xs12" style="padding: 0.75rem;">
                <va-card>
                    <va-card-title>График температуры</va-card-title>
                    <va-card-content>
                        <Line id="my-chart-id" :data="dataChart" :options="options" />
                    </va-card-content>
                </va-card>
            </div>
        </div>
    </va-card>
</template>

<style>
.va-card__title {
  font-size: 18px
}
.va-card__content {
  font-size: 18px
}
</style>

<script lang="ts">
import { Line } from 'vue-chartjs'
import { Chart, PointElement, CategoryScale, LinearScale, LineController, LineElement } from 'chart.js'

Chart.register(PointElement, CategoryScale, LinearScale, LineController, LineElement )

export default {
components: { Line },
  data () {
    return {
        dataChart: {
            labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
            datasets: [
                {
                label: 'Data One',
                backgroundColor: '#f87979',
                data: [40, 39, 10, 40, 39, 80, 40]
                }
            ]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false
        }
    }
  },
}
</script>