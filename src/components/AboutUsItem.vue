<template>
    <div class="gridItem">
        <h3 class="title">{{title}}</h3>
        <p class="content">{{message}}</p>
        <fa class="icon" :icon=icon />
    </div>
</template>
<script>
export default {
    name: 'AboutUsItem',
    props: ['title', 'icon', 'message']
}
</script>
<style lang="scss" scoped>
@import '../assets/scss/style.scss';
    .gridItem{
        width:600px;
        height: 300px;
        border-radius:0 25px 0 25px;
        background-color: #212121;
        color: $color-white;
        -webkit-box-shadow: 0px 0px 15px 0px $red-details; 
        box-shadow: 0px 0px 15px 0px $red-details;
        display:flex;
        flex-direction:column;
        justify-content: center;
        align-items: center;

        & > .title{
            font-size: $first-title;
        }

        & > .content{
            padding: 20px;
        }

        & > .icon{
            font-size: $icon-size;
        }

    }
</style>