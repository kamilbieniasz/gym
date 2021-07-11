<template>
    <section class="parallaxWrapper" :style="{'background-image': 'url(' + require(`../assets${bgImageJpg}`)+')', 'background-image': '-webkit-image-set(url(' + require(`../assets${bgImageWebp}`) + ')1x )'}">
    </section>
</template>
<script>
export default {
    name: "Parallax",
    props: ['bgImageJpg', 'bgImageWebp']
}
</script>
<style lang="scss" scoped>
    @import "../assets/scss/style.scss";
    .parallaxWrapper{
        height:50vh;
        // background-image: url('../assets/images/parallax/parallax1.jpg');
        background-attachment: fixed;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
    }
</style>
