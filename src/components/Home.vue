<template>
    <section class="homeWrapper">
        <h1>Gym Master</h1>
    </section>
</template>
<script>
export default {
    
}
</script>
<style lang="scss" scoped>
    @import "../assets/scss/style.scss";

    .homeWrapper{
        background-size: cover;
        height:100vh !important;
        background-image: url('../assets/images/home/home.jpg');
        background-image: -webkit-image-set(url('../assets/images/home/home.jpg')1x );
        background-blend-mode: color-burn;
        background-color: rgba($color-dark, 0.3);
        background-position: center;
        background-size: cover;
        display:flex;
        justify-content: center;
        align-items: center;

        & > h1{
            font-size: $icon-size;
            color: $color-white;
            user-select: none;
        }
    }
</style>
