<template>
    <Pie v-if="loadedPie" :data="PieChartData" :options="options" />
</template>
  
<script >

import { Chart as ChartJS, ArcElement, Tooltip, Legend } from 'chart.js'
import { Pie } from 'vue-chartjs'
import axios from 'axios';

ChartJS.register(ArcElement, Tooltip, Legend)

export default {
    data() {
        return {
            apiUrl: 'http://localhost:3000',
            loadedPie: false,
            PieChartData: {
                labels: [],
                datasets: [
                    {

                        data: [],
                        backgroundColor: ['rgba(75, 192, 192, 0.5)', 'rgba(0, 192, 0, 0.5)', 'rgba(75, 192, 0, 0.5)', 'rgba(75, 0, 192, 0.5)', 'rgba(75, 7, 45, 0.5)',],
                    }
                ]
            },
            options: {
                plugins: {
                    title: {
                        display: true,
                        text: 'Operating system',
                        font: {
                            size: 20
                        }
                    },
                    legend: {
                        display: true
                    },
                    responsive: true,


                }
            }

        }
    },
    components: {
        Pie
    },

    methods: {
        pieData() {
            axios.get(this.apiUrl + '/Devices')
                .then((response) => {
                    // handle success
                    console.log(response);
                    response.data.forEach(element => {
                        this.PieChartData.labels.push(element.os);
                        this.PieChartData.datasets[0].data.push(element.connections);
                    });
                    this.loadedPie = true;

                    console.log(this.PieChartData.labels);
                })
                .catch((error) => {
                    // handle error
                    console.log(error);
                })
                .finally(() => {
                    // always executed
                });
        }
    },
    mounted() {
        this.pieData();
    },

}



</script>
  

<style lang="scss" scoped></style>