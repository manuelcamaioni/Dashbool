<template>
    <div class="container-fluid sidebar">
        <div class="sidebar-info">
            <h3 class="my-3">~ Dashbool ~</h3>
            <div class="user-cont">
                <div class="img-cont">
                    <img src="https://i.pinimg.com/564x/d1/4a/b5/d14ab57b9ddcfa1240ffabd13f8b609c.jpg" alt="User image //">
                </div>
                <div class="py-3 ms-3">
                    <p class="m-0">Welcome</p>
                    <p class="m-0 fw-bold">Mario Rossi</p>
                </div>
            </div>
            <h4 class="mt-3">GENERAL</h4>
            <hr class="my-1">
            <div class="accordion accordion-flush" id="accordionFlushExample">
                <div class="accordion-item">
                    <h2 class="accordion-header" id="flush-headingOne">
                        <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse"
                            data-bs-target="#flush-collapseOne" aria-expanded="false" aria-controls="flush-collapseOne">
                            Home
                        </button>
                    </h2>
                    <div id="flush-collapseOne" class="accordion-collapse collapse" aria-labelledby="flush-headingOne"
                        data-bs-parent="#accordionFlushExample">
                        <div class="accordion-body">Placeholder content for this accordion, which is intended to demonstrate
                            the <code>.accordion-flush</code> class. This is the first item's accordion body.</div>
                    </div>
                </div>
                <div class="accordion-item">
                    <h2 class="accordion-header" id="flush-headingTwo">
                        <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse"
                            data-bs-target="#flush-collapseTwo" aria-expanded="false" aria-controls="flush-collapseTwo">
                            Maps
                        </button>
                    </h2>
                    <div id="flush-collapseTwo" class="accordion-collapse collapse" aria-labelledby="flush-headingTwo"
                        data-bs-parent="#accordionFlushExample">
                        <div class="accordion-body">Placeholder content for this accordion, which is intended to demonstrate
                            the <code>.accordion-flush</code> class. This is the second item's accordion body. Let's imagine
                            this being filled with some actual content.</div>
                    </div>
                </div>
                <div class="accordion-item">
                    <h2 class="accordion-header" id="flush-headingThree">
                        <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse"
                            data-bs-target="#flush-collapseThree" aria-expanded="false" aria-controls="flush-collapseThree">
                            Config
                        </button>
                    </h2>
                    <div id="flush-collapseThree" class="accordion-collapse collapse" aria-labelledby="flush-headingThree"
                        data-bs-parent="#accordionFlushExample">
                        <div class="accordion-body">Placeholder content for this accordion, which is intended to demonstrate
                            the <code>.accordion-flush</code> class. This is the third item's accordion body. Nothing more
                            exciting happening here in terms of content, but just filling up the space to make it look, at
                            least at first glance, a bit more representative of how this would look in a real-world
                            application.</div>
                    </div>
                </div>
                <div class="accordion-item">
                    <h2 class="accordion-header" id="flush-headingFour">
                        <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse"
                            data-bs-target="#flush-collapseFour" aria-expanded="false" aria-controls="flush-collapseFour">
                            Contacts
                        </button>
                    </h2>
                    <div id="flush-collapseFour" class="accordion-collapse collapse" aria-labelledby="flush-headingFour"
                        data-bs-parent="#accordionFlushExample">
                        <div class="accordion-body">Placeholder content for this accordion, which is intended to demonstrate
                            the <code>.accordion-flush</code> class. This is the third item's accordion body. Nothing more
                            exciting happening here in terms of content, but just filling up the space to make it look, at
                            least at first glance, a bit more representative of how this would look in a real-world
                            application.</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
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
.sidebar {
    background-color: #242424;
    height: 100vh;
    width: 20%;
    position: fixed;
    left: 0;
    z-index: 1;

    .sidebar-info {
        color: #fff;
        display: flex;
        flex-direction: column;
    }

    .user-cont {
        display: flex;
        justify-content: start;

        .img-cont {
            width: 30%;
            border-radius: 50%;
            overflow: hidden;


            img {
                width: 100%;
                object-fit: cover;
            }
        }
    }

    .accordion-button {
        background-color: #242424;
        color: #fff;

        &:focus {
            border-color: none;
        }
    }
}
</style>