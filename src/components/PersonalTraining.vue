<template>
    <section class="personalTrainingWrapper">
        <h2 class="title">Trening personalny</h2>
        <div class="descriptionContainer">
            <div class="description">
                <ul>
                    <li>Dopiero zaczynasz i nie wiesz jak się do tego zabrać?</li>
                    <li>Masz problem z ułożeniem planu treningowego pod siebie?</li>
                    <li>Nie wiesz jak ułożyć dietę aby osiągnąć swój cel?</li>
                    <li>Szukasz nowych inspiracji?</li>
                    <li>Przez rutynę na treningach brakuje ci motywacji?</li>
                </ul>
                <h2>Jeżeli jedno z powyższych pytań dotyczy Ciebie zapytaj o darmowy, próbny trening w naszej recepcji. Nasi trenerzy chętnie odpowiedzą na te i inne pytania oraz we wszystkim Ci pomogą.</h2>
            </div>
            <picture>
                <source srcset="../assets/images/personalTraining/personal_training.webp" type="image/webp">
                <source srcset="../assets/images/personalTraining/personal_training.jpg" type="image/jpeg">
                <img src="../assets/images/personalTraining/personal_training.jpg" />
            </picture>
        </div>
        <div class="gridContainer">
            <GridItemLayer icon="id-card" title="Posiadamy wykwalifikowaną kadrę" bgImageJpg="/images/personalTraining/1.jpg" bgImageWebp="/images/personalTraining/1.webp" />
            <GridItemLayer icon="id-card" title="Każdy z naszych trenerów ukończył dodatkowe kursy" bgImageJpg="/images/personalTraining/2.jpg" bgImageWebp="/images/personalTraining/2.webp" />
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
        height:100%;
        height:50%;
        display:flex;
        align-items: center;

        & > .description{
            width:50%;
            height:100%;
            // padding: 40px;
            display:flex;
            flex-direction: column;
            align-items: left;
            justify-content: space-evenly;
            color: $color-white;
            background-color: $color-dark;

            & > ul{ 
                margin: 0;
                padding: 0 80px;

                & > li{
                    font-size: $medium-font;
                }
            }

            & > h2{
                padding:0 40px;
            }
        }
        
        & > picture{
            width:50%;
            height:100%;
            
            & > img{
                width:100%;
                height:100%;
                object-fit: cover;
                object-position: center;
            }
        }

    }

    & > .gridContainer{
        width:100%;
        height:100%;
        display:grid;
        grid-template-columns: repeat(5, 1fr);
    } 
}
    
</style>
