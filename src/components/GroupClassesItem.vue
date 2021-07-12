<template>
    <div class="groupClassesItem" :style="{'background-image': 'url(' + require(`../assets${bgImageJpg}`)+')', 'background-image': '-webkit-image-set(url(' + require(`../assets${bgImageWebp}`) + ')1x )'}">
        <h2 class="title">{{title}}</h2>
    </div>
</template>
<script>
export default {
    name: "GroupClassesItem",
    props:['bgImageJpg', 'bgImageWebp', 'title']
}
</script>
<style lang="scss" scoped>
@import '../assets/scss/style.scss';
    .groupClassesItem{
        width:100%;
        height:100%;
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;

        display:flex;
        align-items: flex-end;
        justify-content: center;

        border:2px solid $color-white;

        @include respond-to(max-width, 1024px){
            min-height: 200px;
            border: none;
        }

        @include respond-to(max-width, 768px){
            // justify-content: flex-end;
        }

        &:hover .title {
            transform: scale(1.2);
            transition: 300ms ease-in-out;

            @include respond-to(max-width, 768px){
                transform: scale(1);
            }
        }

        & > .title{
            background-color: $color-dark;
            margin: 10px 0;
            padding:10px 20px;
            color: $color-white;
            -webkit-box-shadow: $shadow-box; 
            box-shadow: $shadow-box;
            transition: 300ms ease-in-out;

            @include respond-to(max-width, 768px){
                padding: 0;
            }
        }
    }
</style>
