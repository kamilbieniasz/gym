<template>
    <section class="parallaxWrapper"></section>
</template>
<script>
import {computed, toRefs} from "vue";

export default {
    name: "Parallax",
    props: ['backgroundImage'],
    setup(props) {
      const { backgroundImage } = toRefs(props);

      const backgroundImageStyle = computed(() => {
        return `url(/parallax/${backgroundImage.value})`;
      });

      return {
        backgroundImageStyle,
      };
    }
}
</script>
<style lang="scss" scoped>
  @import "../assets/scss/colors.scss";

  .parallaxWrapper{
        height: 50dvh;
        background-image: v-bind(backgroundImageStyle);
        background-attachment: fixed;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        box-shadow: inset 0 0 200px 50px $color-black;
    }
</style>
