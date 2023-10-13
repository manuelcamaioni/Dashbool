<template>
    <Line v-if="loadedLine" id="line-chart" :data="LineChartData" />
</template>

<script>
import axios from 'axios';
import { Line } from 'vue-chartjs'
import {
    Chart as ChartJS,
    CategoryScale,
    LinearScale,
    PointElement,
    LineElement,
    Title,
    Tooltip,
    Legend,
    Filler
} from 'chart.js'
ChartJS.register(
    CategoryScale,
    LinearScale,
    PointElement,
    LineElement,
    Title,
    Tooltip,
    Legend,
    Filler
)
export default {
    data() {
        return {
            LineChartData: {
                labels: [],
                datasets: [
                    {
                        label: 'Monthly',
                        fill: true, // Abilita il riempimento dell'area sottostante la linea
                        backgroundColor: 'rgba(75, 192, 192, 0.2)', // Colore dell'area
                        borderColor: 'rgba(75, 192, 192, 1)',
                        borderWidth: 1,
                        tension: 0.4,
                        borderRadius: 50,
                        data: [],
                    }
                ]
            },


            apiUrl: 'http://localhost:3000',
            loadedLine: false
        }
    },
    components: { Line },
    mounted() {
        this.getDataCharts();
    },
    methods: {
        getDataCharts() {
            axios.get(this.apiUrl + '/MonthlyConnections')
                .then((response) => {
                    // handle success
                    console.log(response);

                    response.data.forEach(element => {
                        this.LineChartData.labels.push(element.month);
                        this.LineChartData.datasets[0].data.push(element.connections)


                    });
                    this.loadedLine = true;
                })
                .catch((error) => {
                    // handle error
                    console.log(error);
                })
                .finally(function () {
                    // always executed
                });
        }
    }
}
</script>

<style lang="scss" scoped></style>