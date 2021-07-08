<template>
    <section class="homeWrapper">
        <video autoplay loop muted>
            <source src="../assets/movie/backgroundVideo.mp4" />
        </video>
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
        height:60vh;

        & > video{
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
    }
</style>