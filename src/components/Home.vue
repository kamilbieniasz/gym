<template>
    <section id="home" class="homeWrapper">
        <h1>Gym Master</h1>
        <h2>Siłownia dla każdego</h2>
    </section>
</template>
<script>
export default {
    
}
</script>
<style lang="scss" scoped>
    @import "../assets/scss/style.scss";

    .homeWrapper{
        height: 100dvh;
        background-image: url('../assets/images/home/home.jpg');
        background-blend-mode: color-burn;
        background-color: rgba($color-dark, 0.3);
        background-position: center;
        background-size: cover;
        display:flex;
        justify-content: center;
        align-items: center;

        //@include respond-to(max-width, 768px){
        //    height: 40vh;
        //}

        & > h1 {
            font-size: 4rem;
            color: $color-white;
            user-select: none;
            margin-bottom: 0;
        }

        & > h2 {
            color: $color-white;
            font-size: 2rem;
        }
    }
</style>
