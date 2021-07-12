<template>
    <section class="personalTrainingWrapper">
        <h2 class="title">Trening personalny</h2>
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
                <source srcset="../assets/images/personalTraining/personal_training.webp" type="image/webp">
                <source srcset="../assets/images/personalTraining/personal_training.jpg" type="image/jpeg">
                <img src="../assets/images/personalTraining/personal_training.jpg" />
            </picture>
        </div>
        <div class="gridContainer">
            <GridItemLayer icon="id-card" title="Posiadamy wykwalifikowaną kadrę" bgImageJpg="/images/personalTraining/1.jpg" bgImageWebp="/images/personalTraining/1.webp" />
            <GridItemLayer icon="id-card" title="Trening jest dopasowany do twoich potrzeb" bgImageJpg="/images/personalTraining/3.jpg" bgImageWebp="/images/personalTraining/3.webp" />
            <GridItemLayer icon="id-card" title="Idywidualnie ułożona dietaę" bgImageJpg="/images/personalTraining/4.jpg" bgImageWebp="/images/personalTraining/4.webp" />
            <GridItemLayer icon="id-card" title="Kontakt z trenerem nie tylko na treningachę" bgImageJpg="/images/personalTraining/5.jpg" bgImageWebp="/images/personalTraining/5.webp" />
        </div>
    </section>
</template>
<script>
import GridItemLayer from './GridItemLayer';
export default {
    name: "PersonalTraining",
    components: {
        GridItemLayer
    }
}
</script>
<style lang="scss" scoped>
@import '../assets/scss/style.scss';

.personalTrainingWrapper{

    & > .descriptionContainer{
        width:100%;
        height:50%;
        display:flex;

        & > .description{
            width:50%;
            display:flex;
            flex-direction: column;
            justify-content: space-evenly;
            background-color: $color-dark;
            color: $color-white;

            @include respond-to(max-width, 1024px){
                padding: 40px 0;
            }

            @include respond-to(max-width, 768px){
                width:100%;
            }

            & > ul{ 
                margin: 0;
                padding: 0 80px;

                & > li{
                    font-size: $medium-font;
                }
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
