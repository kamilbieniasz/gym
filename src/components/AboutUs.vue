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
                <GridItemLayer 
                    title="Dostęp 24/7" 
                    description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium cumque harum tempora tenetur architecto facilis quas iste facere dolores reiciendis! Quidem reprehenderit voluptatibus omnis, consectetur vero soluta officiis architecto eius!" 
                    bgImageJpg="/images/aboutUs/1.jpg"
                    bgImageWebp="/images/aboutUs/1.webp"/>

                <GridItemLayer 
                    title="Karnet szyty na miarę" 
                    description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium cumque harum tempora tenetur architecto facilis quas iste facere dolores reiciendis! Quidem reprehenderit voluptatibus omnis, consectetur vero soluta officiis architecto eius!" 
                    bgImageJpg="/images/aboutUs/2.jpg"
                    bgImageWebp="/images/aboutUs/2.webp"/>
                
                <GridItemLayer 
                    title="Najlepszy sprzęt" 
                    description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium cumque harum tempora tenetur architecto facilis quas iste facere dolores reiciendis! Quidem reprehenderit voluptatibus omnis, consectetur vero soluta officiis architecto eius!" 
                    bgImageJpg="/images/aboutUs/3.jpg"
                    bgImageWebp="/images/aboutUs/3.webp"/>

                <GridItemLayer 
                    title="Plan treningowy" 
                    description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium cumque harum tempora tenetur architecto facilis quas iste facere dolores reiciendis! Quidem reprehenderit voluptatibus omnis, consectetur vero soluta officiis architecto eius!" 
                    bgImageJpg="/images/aboutUs/4.jpg"
                    bgImageWebp="/images/aboutUs/4.webp"/>
                <!-- <div class="gridItem">
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
                </div> -->

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
import GridItemLayer from './GridItemLayer';

export default {
    name: 'AboutUs',
    components: {
        // CardItem,
        GridItemLayer
    }
    
}
</script>
<style lang="scss" scoped>
@import "../assets/scss/style.scss";


.aboutUsWrapper{
    width:100%;

    @include respond-to(max-width, 1024px){
        height:fit-content;
        flex-direction: column;
    }

    & > .descriptionContainer{
        width:100%;
        height:50%;
        display:flex;
        justify-content: center;

        @include respond-to(max-width, 768px){
            flex-direction: column;
        }

        & > .description{
            width:50%;
            display:flex;
            flex-direction: column;
            justify-content: space-evenly;
            background-color: $color-dark;
            color: $color-white;

            @include respond-to(max-width, 768px){
                width:100%;
            }

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

            @include respond-to(max-width, 768px){
                display:none;
            }

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

        @include respond-to(max-width, 768px){
            grid-template-columns: repeat(2, 1fr);
        }
    }
}
    
</style>
