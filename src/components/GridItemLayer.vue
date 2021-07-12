<template>
    <div class="gridItem" :style="{'background-image': 'url(' + require(`../assets${bgImageJpg}`)+')', 'background-image': '-webkit-image-set(url(' + require(`../assets${bgImageWebp}`) + ')1x )'}">
        <fa class="icon" v-if="icon" :icon=icon />
        <h2 v-if="title">{{title}}</h2>
        <p v-if="description">{{description}}</p>
    </div>
</template>
<script>
export default {
    name: "GridItemLayer",
    props: ['title', 'description', 'icon', 'bgImageJpg', 'bgImageWebp']
}
</script>
<style lang="scss" scoped>
@import '../assets/scss/style.scss';

.gridItem{
    width:100%;
    height:100%;
    background-size: cover;
    background-position: center;
    background-blend-mode: color-burn;
    color: $color-white;
    display:flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position:relative;
    border-width: 2px 2px 0 2px;
    border-style: solid;
    border-color:$color-white;

    & > .icon{
        font-size: $small-icon-size;
    }

    & > h2{
        text-align:center;
        padding:0 10px;

        @include respond-to(max-width, 768px){
            font-size: $medium-font;
        }
    }

    & > p {
        padding:0 10px;
    }

    &::before{
        content: '';
        width:100%;
        height:100%;
        background-color:rgba($color-dark, 0.7);
        position: absolute;
        transition: 300ms ease-in-out;
    }
                
    &:hover::before{
        transform: scaleY(0.8);
        transition: 300ms ease-in-out;

        @include respond-to(max-width, 768px){
            transform: scaleY(1);
        }
    }

    & > h2, & > p, & > .icon{
        z-index: 10;
    }
}
</style>
