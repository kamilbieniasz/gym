<template>
    <div class="gridItem">
        <div class="content">
            <h3 class="title" v-if="title">{{title}}</h3>
            <p class="content" v-if="message">{{message}}</p>
            <fa v-if="icon" class="icon" :icon=icon />
            <slot></slot>
        </div>

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
        width: 100%;
        height: 100%;
        border-radius:0 25px 0 25px;
        background-color: $color-dark;
        color: $color-white;
        padding: 20px;
        -webkit-box-shadow: $light-shadow-box; 
        box-shadow: $light-shadow-box;

        & > .content{
            width:100%;
            height:100%;
            display:flex;
            flex-direction: column;
            align-items: center;

            & > .title{
                margin:0;
                font-size: $medium-font;
            }

            & > .content{
                padding: 20px;
            }

            & > .icon{
                font-size: $icon-size;
            }
        }
    }
</style>
