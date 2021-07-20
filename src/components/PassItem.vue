<template>
    <div class="pass">
        <h2>{{pass.title}}</h2>
        <ul>
            <li v-for="pass of pass.list" :key="pass">{{pass}}</li>
        </ul>
        <div class="buttonContainer">
            <button>Kup</button>
        </div>
    </div>
</template>
<script>
export default {
    name: "PassItem",
    props: ["pass"]
}
</script>
<style lang="scss" scoped>
@import '../assets/scss/style.scss';

.pass{
    width: 90%;
    height: 60%;
    border: 2px solid $color-white;
    display:flex;
    flex-direction: column;
    background-color:rgba($color-dark, 0.7);

    @include respond-to(max-width, 1024px){
        height:100%;
        margin: 10px 0;
    }

    @include respond-to(max-width, 768px){
        height:fit-content;
        margin: 10px 0;
    }

    &:hover{
        box-shadow: $light-shadow-box;
        -webkit-box-shadow: $light-shadow-box;
        transition: 300ms ease-in-out;
    }

    &:hover .buttonContainer>button{
        opacity:1;
        transition: 300ms ease-in-out;
    }

    & > h2{
        margin:0;
        padding: 20px 0;
        text-align: center;
        background-color: $color-white;
    }

    & > ul{
        height:100%;
        list-style-type: none;
        margin:0;
        padding:10px 5px;

        & > li{
            color: $color-white;
            font-size: $medium-font;

            &::before{
                content:"✓";
                margin: 0 5px;
            }
        }
    }

    & > .buttonContainer{
        display:flex;
        justify-content: center;
        padding:20px 0;

        & > button{
            padding: 10px 30px;
            background-color: transparent;
            border: 2px solid $color-white;
            color: $color-white;
            cursor: pointer;
            opacity: 0;
            transition: 300ms ease-in-out;

            &:hover{
                background-color: $color-white;
                color: $color-dark;
                transition: 300ms ease-in-out;
            }
        }
    }
}
</style>
