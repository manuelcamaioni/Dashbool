<script>
import Sidebar from './components/sidebar.vue';
import Navbar from './components/navbar.vue';
import Charts from './components/chartsIndex.vue';
export default {
  components: {
    Sidebar, Navbar, Charts
  }
}

</script>

<template>
  <Navbar />
  <Sidebar />
  <Charts />
</template>

<style lang="scss">
@import "bootstrap/scss/bootstrap";
</style>
