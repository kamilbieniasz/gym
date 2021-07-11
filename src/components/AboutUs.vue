<template>
    <section class="aboutUsWrapper">
            <h2 class="title">O nas</h2>
            <div class="descriptionContainer">
                <div class="description">
                    <h2>Lorem ipsum</h2>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur omnis dicta voluptatibus optio voluptates sit rerum quos commodi, dolor vel unde quas officiis ratione eaque voluptas, beatae totam reiciendis excepturi.
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur omnis dicta voluptatibus optio voluptates sit rerum quos commodi, dolor vel unde quas officiis ratione eaque voluptas, beatae totam reiciendis excepturi.
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur omnis dicta voluptatibus optio voluptates sit rerum quos commodi, dolor vel unde quas officiis ratione eaque voluptas, beatae totam reiciendis excepturi.
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur omnis dicta voluptatibus optio voluptates sit rerum quos commodi, dolor vel unde quas officiis ratione eaque voluptas, beatae totam reiciendis excepturi.
                    </p>
                </div>
                <picture>
                    <source srcset="../assets/images/aboutUs/main.webp" type="image/webp">
                    <source srcset="../assets/images/aboutUs/main.jpg" type="image/jpeg">
                    <img src="../assets/images/aboutUs/main.jpg" />
                </picture>
            </div>
            <div class="gridContainer">
                <div class="gridItem">
                    <h2>Dostęp 24/7</h2>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium cumque harum tempora tenetur architecto facilis quas iste facere dolores reiciendis! Quidem reprehenderit voluptatibus omnis, consectetur vero soluta officiis architecto eius!</p>
                </div>
                <div class="gridItem">
                    <h2>Karnet szyty na miarę</h2>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium cumque harum tempora tenetur architecto facilis quas iste facere dolores reiciendis! Quidem reprehenderit voluptatibus omnis, consectetur vero soluta officiis architecto eius!</p>
                </div>
                <div class="gridItem">
                    <h2>Najlepszy sprzęt</h2>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium cumque harum tempora tenetur architecto facilis quas iste facere dolores reiciendis! Quidem reprehenderit voluptatibus omnis, consectetur vero soluta officiis architecto eius!</p>
                </div>
                <div class="gridItem">
                    <h2>Plan treningowy</h2>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium cumque harum tempora tenetur architecto facilis quas iste facere dolores reiciendis! Quidem reprehenderit voluptatibus omnis, consectetur vero soluta officiis architecto eius!</p>
                </div>

                <!-- <CardItem 
                title="Dostęp 24/7" 
                icon="clock"
                message="Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita odio eum fugit, sit eaque distinctio commodi neque cum nesciunt architecto vero recusandae sequi corrupti fugiat quos veritatis repudiandae dignissimos animi." />
                <CardItem 
                title="Karnet szyty na miarę" 
                icon="calendar" 
                message="Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita odio eum fugit, sit eaque distinctio commodi neque cum nesciunt architecto vero recusandae sequi corrupti fugiat quos veritatis repudiandae dignissimos animi." />
                <CardItem 
                title="Najlepszy sprzęt" 
                icon="dumbbell" 
                message="Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita odio eum fugit, sit eaque distinctio commodi neque cum nesciunt architecto vero recusandae sequi corrupti fugiat quos veritatis repudiandae dignissimos animi." />
                <CardItem 
                title="Plan treningowy" 
                icon="clipboard" 
                message="Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita odio eum fugit, sit eaque distinctio commodi neque cum nesciunt architecto vero recusandae sequi corrupti fugiat quos veritatis repudiandae dignissimos animi." /> -->
            </div>
    </section>
</template>
<script>
// import CardItem from './CardItem';

export default {
    name: 'AboutUs',
    components: {
        // CardItem,
    }
    
}
</script>
<style lang="scss" scoped>
@import "../assets/scss/style.scss";


.aboutUsWrapper{
    width:100%;

    & > .descriptionContainer{
        width:100%;
        height:50%;
        display:flex;
        justify-content: center;
        & > .description{
            width:50%;
            display:flex;
            flex-direction: column;
            justify-content: space-evenly;
            background-color: $color-dark;
            color: $color-white;

            & > h2 {
                font-size: $bigger-font;
                text-align: center;
            }

            & > p {
                font-size: $medium-font;
                padding:0 40px;
            }
        }

             & > picture{
            width:50%;

            & > img{
                width:100%;
                height:100%;
                object-fit:cover;
                object-position: center;
            }
        }
    }

    & > .gridContainer{
        width:100%;
        height:50%;
        display:grid;
        grid-template-columns: repeat(4, 1fr);
        justify-items: center;
        align-items: center;
        text-align: center;

        & > .gridItem{
            width:100%;
            height:100%;
            background-size: cover;
            background-position: center;
            background-blend-mode: color-burn;
            color: $color-white;
            display:flex;
            flex-direction: column;
            justify-content: center;
            position:relative;
            border-width: 2px 2px 0 2px;
            border-style: solid;
            border-color:$color-white;

            &:nth-child(1){
                background-image: url('../assets/images/aboutUs/1.jpg');
                background-image: -webkit-image-set(url('../assets/images/aboutUs/1.webp')1x );
            }

            &:nth-child(2){
                background-image: url('../assets/images/aboutUs/2.jpg');
                background-image: -webkit-image-set(url('../assets/images/aboutUs/2.webp')1x );
            }

            &:nth-child(3){
                background-image: url('../assets/images/aboutUs/3.jpg');
                background-image: -webkit-image-set(url('../assets/images/aboutUs/3.webp')1x );
            }

            &:nth-child(4){
                background-image: url('../assets/images/aboutUs/4.jpg');
                background-image: -webkit-image-set(url('../assets/images/aboutUs/4.webp')1x );
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
                transform: scaleY(0.7);
                transition: 300ms ease-in-out;
            }

            & > h2, & > p{
                z-index: 10;
            }
        }
    }
}
    
</style>
