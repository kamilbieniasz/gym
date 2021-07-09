<template>
    <div class="groupClassesItem" :style="{'background-image': 'url(' + require(`../assets${image}`) + ')'}">
        <h2 class="title">{{title}}</h2>
    </div>
</template>
<script>
export default {
    name: "GroupClassesItem",
    props:['image', 'title']
}
</script>
<style lang="scss" scoped>
@import '../assets/scss/style.scss';
    .groupClassesItem{
        width:300px;
        height:400px;
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;

        display:flex;
        align-items: flex-end;
        justify-content: flex-end;

        border-radius: 0 25px 0 25px;
        border:2px solid black;

        &:hover .title {
            transform: scale(1.2);
            transition: 300ms ease-in-out;
        }

        & > .title{
            background-color: $color-dark;
            margin: 0;
            padding:10px 20px;
            color: $color-white;
            margin: -10px -10px;
            -webkit-box-shadow: $shadow-box; 
            box-shadow: $shadow-box;
            transition: 300ms ease-in-out;
        }
    }
</style>
