<template>
    <div class="square">
        <fa v-if="icon" class="icon" :icon=icon />
        <h3 v-if="text">{{text}}</h3>
    </div>
</template>
<script>
export default {
    name: "PersonalTrainingItem",
    props: ["icon", "text"]
    
}
</script>
<style lang="scss" scoped>
@import '../assets/scss/style.scss';

.square{
    width:100%;
    height:100%;
    background-color: $color-dark;
    color: $color-white;
    display:flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 15px 0;
    border:2px solid $color-white;
    // -webkit-box-shadow: $shadow-box; 
    // box-shadow: $shadow-box;
    transition: 300ms ease-in-out;

    &:first-child{
        border-left:none;
    }
    &:last-child{
        border-right: none;
    }

    // &:hover{
    //     transform: scale(1.1);
    //     transition: 300ms ease-in-out;
    // }

    & > .icon{
        font-size: $icon-size;
    }

    & > h3{
        text-align: center;
        font-size: $medium-font;
    }
}
    
</style>
