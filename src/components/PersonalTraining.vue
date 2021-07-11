<template>
    <section class="personalTrainingWrapper">
        <div class="sectionContent">
            <div class="title">
                <h2>Trening personalny</h2>
            </div>
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
            <div class="gridContainer">
                <PersonalTrainingItem icon="medal" text="Posiadamy wykwalifikowaną kadrę"/>
                <PersonalTrainingItem icon="id-card" text="Każdy z naszych trenerów ukończył dodatkowe kursy"/>
                <PersonalTrainingItem icon="align-left" text="Trening jest dopasowany do twoich potrzeb"/>
                <PersonalTrainingItem icon="apple-alt" text="Idywidualnie ułożona dieta"/>
                <PersonalTrainingItem icon="envelope" text="Kontakt z trenerem nie tylko na treningach"/>
            </div>
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
    & > .sectionContent{
        display: flex;
        flex-direction: column;
        align-items:center;

        & > .description{
            width:50%;
            padding: 40px;
            display:flex;
            flex-direction: column;
            align-items: center;

            & > ul{ 
                margin: 0;

                & > li{
                    font-size: $medium-font;
                }
            }
            & > h2 {
                text-align: center;
            }
        }

        & > .gridContainer{
            margin-top:60px;
            display:grid;
            grid-gap:30px;
            grid-template-columns: repeat(5, 1fr);
        } 
    }
}
    
</style>
