<script>
export default {
    name: 'AppHeader'
}
</script>

<template>
    <header>
        <nav class="navbar bg-body-tertiary d-flex justify-content-start">
            <div class="container-fluid">
                <div class="container-image d-flex">
                    <img src="../assets/img/logo.jpg" class="img-fluid w-25" alt="">

                    <h5>Yu-Gi-Oh API</h5>
                </div>
            </div>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
@use '../styles/main.scss' as *;
@use '../styles/partials/reset.scss' as *;

.container-image {
    width: 40%;

    h5 {
        font-size: 3rem;
    }
}
</style>