<template>
    <section class="passesWrapper">
        <h2 class="title">Karnety</h2>
        <div class="gridContainer">
            <PassItem :pass="open" />
            <PassItem :pass="eight_entries" />
            <PassItem :pass="sixteen_entries" />
            <PassItem :pass="morning" />
            <PassItem :pass="annual" />
            <!-- <div class="pass">
                <h2>Open</h2>
                <ul>
                    <li>wejście o każdej porze</li>
                    <li>nieograniczona ilość wejść</li>
                    <li>nieograniczony czas spędzany na siłowni</li>
                    <li>darmowa sauna</li>
                    <li>darmowy jeden trening z trenerem personalnym</li>
                    <li>karnet ważny miesiąc</li>
                </ul>
                <div class="buttonContainer">
                    <button>Kup</button>
                </div>
            </div>
            <div class="pass"></div>
            <div class="pass"></div>
            <div class="pass"></div>
            <div class="pass"></div> -->
            
                <!-- <CardItem title="Open">
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
                </CardItem> -->
        </div>
    </section>
</template>
<script>
import {ref} from 'vue';
import PassItem from './PassItem';
// import CardItem from './CardItem.vue';

export default {
    name: "Passes",
    components: {
        PassItem
        // CardItem
    },
    setup() {
        const open = ref({
            title:"Open", 
            list:[
                "wejście o każdej porze", 
                "nieograniczona ilość wejść", 
                "nieograniczony czas spędzany na siłowni", 
                "darmowa sauna", 
                "darmowy jeden trening z trenerem personalnym", 
                "karnet ważny miesiąc"
            ]
        });

        const eight_entries = ref({
            title: "8 wejść",
            list: [
                "wejście o każdej porze",
                "nieograniczony czas spędzany na siłowni",
                "karnet ważny przez 3 miesiące"
            ]
        });

        const sixteen_entries = ref({
            title: "16 wejść",
            list: [
                "wejście o każdej porze",
                "nieograniczony czas spędzany na siłowni",
                "darmowa sauna",
                "karnet ważny przez 6 miesięcy"
            ]
        });

        const morning = ref({
            title: "Poranny",
            list: [
                "wejście do godziny 12:00",
                "nieograniczona ilość wejść",
                "nieograniczony czas spędzany na siłowni",
                "darmowa sauna",
                "darmowy jeden trening z trenerem personalnym",
                "karnet ważny miesiąc"
            ]
        });

        const annual = ref({
            title: "Roczny",
            list: [
                "wejście o każdej porze",
                "nieograniczona ilość wejść",
                "nieograniczony czas spędzany na siłowni",
                "darmowa sauna",
                "darmowy miesiąc treningów z trenerem personalnym",
                "darmowe rozpisanie diety",
                "karnet ważny rok"
            ]
        })

        return {open, eight_entries, sixteen_entries, morning, annual}
    }
}
</script>
<style lang="scss" scoped>
    @import "../assets/scss/style.scss";

    .passesWrapper{
        width: 100%;
        // padding: 10px 0;

        & > .gridContainer{
            width:100%;
            height:100%;
            display:grid;
            grid-template-columns: repeat(5, 1fr);
            justify-content: center;
            justify-items: center;
            align-items: center;
            // background-color:$color-dark;
            background-image: url('../assets/images/pass/pass.jpg');
            background-image: -webkit-image-set(url('../assets/images/pass/pass.webp')1x );
            background-size: cover;
            background-position: center;
        }
    }

    
</style>
