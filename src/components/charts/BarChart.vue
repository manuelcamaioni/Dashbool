<template>
    <Bar v-if="loadedBar" id="bar-chart" class="barchart" :data="BarChartData" :options="options" />
</template>

<script>
import axios from 'axios';
import { Bar } from 'vue-chartjs'
import {
    Chart as ChartJS,
    Title,
    Tooltip,
    BarElement,
    CategoryScale,
    LinearScale,

} from 'chart.js'
ChartJS.register(
    Title,
    Tooltip,
    BarElement,
    CategoryScale,
    LinearScale,
)
export default {
    data() {
        return {
            BarChartData: {
                labels: [],
                datasets: [
                    {

                        backgroundColor: ['rgba(75, 192, 192, 0.5)', 'rgba(0, 192, 0, 0.5)', 'rgba(75, 192, 0, 0.5)', 'rgba(75, 0, 192, 0.5)', 'rgba(75, 76, 45, 0.5)',],
                        borderWidth: 1,
                        data: [],
                    }
                ]
            },
            options: {
                plugins: {
                    title: {
                        display: true,
                        text: 'Users Age',
                        font: {
                            size: 20
                        }
                    },
                    legend: {
                        display: false
                    }
                },
                responsive: true,


            },

            apiUrl: 'http://localhost:3000',
            loadedBar: false
        }
    },
    components: { Bar },
    mounted() {
        this.barData();
    },
    methods: {
        barData() {
            axios.get(this.apiUrl + '/UsersAgeRange')
                .then((response) => {
                    // handle success
                    console.log(response);

                    response.data.forEach(element => {
                        this.BarChartData.labels.push(element.range);
                        this.BarChartData.datasets[0].data.push(element.connections)


                    });
                    this.loadedBar = true;
                })
                .catch((error) => {
                    // handle error
                    console.log(error);
                })
                .finally(function () {
                    // always executed
                });
        }
    },
}
</script>

<style lang="scss" scoped></style>