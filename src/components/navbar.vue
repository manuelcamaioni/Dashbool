<template>
    <nav class="d-flex justify-content-between align-items-center">
        <div class="menu-icon ms-3">
            <i class="fa-solid fa-bars fa-lg"></i>
        </div>
        <div class="user-log d-flex align-items-center gap-2 me-3">
            <i class="fa-regular fa-envelope"></i>
            <img class="user-img" src="https://i.pinimg.com/564x/d1/4a/b5/d14ab57b9ddcfa1240ffabd13f8b609c.jpg" alt="">
            <p class="mb-0">Mario Rossi</p>
        </div>
    </nav>
</template>

<script>
export default {
    data() {
        return {

        }
    }
}
</script>

<style lang="scss" scoped>
nav {
    position: absolute;
    right: 0;
    width: 80%;
    height: 4rem;
    background-color: rgb(198, 198, 198);

    .user-img {
        width: 2rem;
        height: 2rem;
        border-radius: 50%;
    }
}
</style>