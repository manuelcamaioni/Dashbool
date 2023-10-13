<template>
    <section>
        <h1 class="text-center">Monthly connections</h1>
        <div class="container mb-4">
            <LineChart class="w-100 h-100" />
        </div>
        <div class="d-flex align-items-center">
            <div class="charts-container">
                <BarChart class="w-100 h-100" />
            </div>
            <div class="charts-container">
                <PieChart class="w-75 m-auto h-100" />
            </div>
        </div>

    </section>
</template>

<script>
import LineChart from './charts/LineChart.vue';
import BarChart from './charts/BarChart.vue';
import PieChart from './charts/PieChart.vue';
export default {
    components: { LineChart, BarChart, PieChart }
}
</script>

<style lang="scss" scoped>
section {
    width: 80%;
    position: absolute;
    right: 0;
    margin-top: 4rem;

    h1 {
        background-color: rgb(227, 227, 227);
        padding: 1rem 0;
    }

    .charts-container {
        width: 50%;
    }



}
</style>