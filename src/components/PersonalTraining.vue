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
            <PersonalTrainingItem icon="medal" text="Posiadamy wykwalifikowaną kadrę"/>
            <PersonalTrainingItem icon="id-card" text="Każdy z naszych trenerów ukończył dodatkowe kursy"/>
            <PersonalTrainingItem icon="align-left" text="Trening jest dopasowany do twoich potrzeb"/>
            <PersonalTrainingItem icon="apple-alt" text="Idywidualnie ułożona dieta"/>
            <PersonalTrainingItem icon="envelope" text="Kontakt z trenerem nie tylko na treningach"/>
        </div>
    </section>
</template>
<script>
import PersonalTrainingItem from './personalTrainingItem.vue';
export default {
    name: "PersonalTraining",
    components: {
        PersonalTrainingItem
    }
}
</script>
<style lang="scss" scoped>
@import '../assets/scss/style.scss';

.personalTrainingWrapper{
    background-color: $color-dark;

    & > .descriptionContainer{
        display:flex;
        height:45%;

        & > .description{
            width:50%;
            height:fit-content;
            padding: 40px;
            display:flex;
            flex-direction: column;
            align-items: left;
            color: $color-white;

            & > ul{ 
                margin: 0;

                & > li{
                    font-size: $medium-font;
                }
            }
        }
        
        & > picture{
            width:50%;
            height:10 0%;
            
            & > img{
                width:100%;
                height:100%;
                object-fit: cover;
                object-position: center;
            }
        }

    }

    & > .gridContainer{
        margin-top:60px;
        display:grid;
        grid-gap:30px;
        grid-template-columns: repeat(5, 1fr);
    } 
}
    
</style>
