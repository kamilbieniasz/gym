<template>
    <nav class="navbar">
        <a>O nas</a>
        <a>Cennik</a>
        <a>Zajęcia grupowe</a>
        <a>Trening personalny</a>
        <a>Kontakt</a>
    </nav>
</template>
<script>
export default {
name: "Navbar"
}

</script>
<style lang="scss" scoped>
@import '../../assets/scss/style.scss';

.navbar{
    width: 100vw;
    display: flex;
    justify-content: center;
    background-color: transparent;
    position: fixed;

    & > a {
        padding: 20px;
        color: white;
        font-size: $bigger-font;
        transition: 300ms easy-in-out;
        cursor: pointer;

        &:hover{
            transform: scale(1.1);
            transition: 300ms easy-in-out;
        }
    }
}
    
</style>