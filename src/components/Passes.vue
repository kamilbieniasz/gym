<template>
    <section id="passes" class="passesWrapper">
        <h2 class="title">Karnety</h2>
        <div class="gridContainer">
            <PassItem :pass="open" />
            <PassItem :pass="eight_entries" />
            <PassItem :pass="sixteen_entries" />
            <PassItem :pass="morning" />
            <PassItem :pass="annual" />
        </div>
    </section>
</template>
<script>
import {ref} from 'vue';
import PassItem from './PassItem';

export default {
    name: "Passes",
    components: {
        PassItem
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

        @include respond-to(max-width, 1024px) {
            height:fit-content;
        }

        & > .gridContainer{
            width:100%;
            height:100%;
            display:grid;
            grid-template-columns: repeat(5, 1fr);
            justify-content: center;
            justify-items: center;
            align-items: center;
            background-image: url('../assets/images/pass/pass.jpg');
            background-image: -webkit-image-set(url('../assets/images/pass/pass.webp')1x );
            background-size: cover;
            background-position: center;

            @include respond-to(max-width, 1024px){
                grid-template-columns: repeat(2, 1fr);
                grid-row-gap: 20px;
                padding: 10px 0;
            }

            @include respond-to(max-width, 768px){
                grid-template-columns: repeat(1, 1fr);
            }
        }
    }

    
</style>
