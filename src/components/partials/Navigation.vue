<template>
    <div class="navigationContainer">
        <button><fa class="icon" icon="arrow-circle-up" /></button>
        <button><fa class="icon" icon="arrow-circle-down" /></button>
    </div>
</template>
<script>
export default {
    
}
</script>
<style lang="scss" scoped>
@import '../../assets/scss/style.scss';

.navigationContainer{
    display:flex;
    flex-direction: column;
    position:fixed;
    right: 5px;
    bottom: 5px;
    z-index:30;

    & > button{
        margin:10px 0;
        padding: 5px 5px;
        border: 2px solid $color-black;
        background-color: $color-white;
        cursor:pointer;

        &:hover{
            box-shadow: $light-shadow-box;
            -webkit-box-shadow: $light-shadow-box; 
        }

        & > .icon{
            font-size: $small-icon-size;
        }
    }
}
    
</style>
