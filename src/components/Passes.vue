<template>
    <section class="passesWrapper">
        <div class="sectionContent">
            <h2 class="title">Karnety</h2>
            <div class="gridContainer">
                <CardItem title="Open">
                    <ul>
                        <li>wejście o każdej porze</li>
                        <li>nieograniczona ilość wejść</li>
                        <li>nieograniczony czas spędzany na siłowni</li>
                        <li>darmowa sauna</li>
                        <li>darmowy jeden trening z trenerem personalnym</li>
                        <li>karnet ważny miesiąc</li>
                    </ul>
                </CardItem>
                <CardItem title="8 wejść">
                    <ul>
                        <li>wejście o każdej porze</li>
                        <li>nieograniczony czas spędzany na siłowni</li>
                        <li>karnet ważny przez 3 miesiące</li>
                    </ul>
                </CardItem>
                <CardItem title="16 wejść">
                    <ul>
                        <li>wejście o każdej porze</li>
                        <li>nieograniczony czas spędzany na siłowni</li>
                        <li>darmowa sauna</li>
                        <li>karnet ważny przez 6 miesięcy</li>
                    </ul>
                </CardItem>
                <CardItem title="Poranny">
                    <ul>
                        <li>wejście do godziny 12:00</li>
                        <li>nieograniczona ilość wejść</li>
                        <li>nieograniczony czas spędzany na siłowni</li>
                        <li>darmowa sauna</li>
                        <li>darmowy jeden trening z trenerem personalnym</li>
                        <li>karnet ważny miesiąc</li>
                    </ul>
                </CardItem>
                <CardItem title="Roczny">
                    <ul>
                        <li>wejście o każdej porze</li>
                        <li>nieograniczona ilość wejść</li>
                        <li>nieograniczony czas spędzany na siłowni</li>
                        <li>darmowa sauna</li>
                        <li>darmowy miesiąc treningów z trenerem personalnym</li>
                        <li>darmowe rozpisanie diety</li>
                        <li>karnet ważny rok</li>
                    </ul>
                </CardItem>
            </div>
        </div>
    </section>
</template>
<script>
import CardItem from './CardItem.vue';

export default {
    name: "Passes",
    components: {
        CardItem
    }
}
</script>
<style lang="scss" scoped>
    @import "../assets/scss/style.scss";

    .passesWrapper{

        & > .sectionContent{

            & > .gridContainer{
            display:grid;
            grid-gap:60px;
            grid-template-columns: repeat(3, 1fr);
            justify-content: center;
            justify-items: center;
            align-items: center;

                & ul{
                    margin:10px 0;
                    padding: 20px;
                    & > li{
                        font-size: $medium-font;
                    }
                }
            }
        }
    }

    
</style>
