<template>
    <section class="contactWrapper">
        <div class="sectionContent">
            <div class="title">
                <h2>Kontakt</h2>
            </div>
            <div class="contactContainer">
                <h3><strong>Telefon:</strong>123 456 789</h3>
                <h3><strong>Email:</strong>gymmaster@gym.pl</h3>
                <h3><strong>Nasza siłownia otwarta jest całodobowo!</strong></h3>
            </div>
            <div class="mapsControls">
                <div class="buttonsContainer">
                    <div class="buttons" v-for="(city, index) in cities" v-bind:key="city">
                        <button @click="showMap(index)">{{city.name}}</button>
                    </div>
                </div>
                <div class="mapContainer">
                    <div class="map" v-for="city in cities" v-bind:key="city">
                        <iframe :src="city.src" v-if="city.status" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
<script>
import {ref} from 'vue';
export default {
    name: "Contact",
    setup(){
        const cities = ref([
            {
                name:"Rzeszów",
                src:"https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d4309.457375788767!2d21.99577232595733!3d50.04098763299425!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x473cfb018c3f4fbd%3A0x5033f39cd685a056!2sGaleria%20Rzesz%C3%B3w!5e0!3m2!1spl!2spl!4v1625845604051!5m2!1spl!2spl",
                status:true
            },
            {
                name:"Kraków",
                src:"https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2561.013013926552!2d19.943849415837256!3d50.067317922777754!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47165b1a8da8ead5%3A0x5c28a58487c0c7fa!2sGaleria%20Krakowska!5e0!3m2!1spl!2spl!4v1625845646440!5m2!1spl!2spl",
                status:false
            },
            {
                name:"Warszawa",
                src:"https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2446.505031679183!2d21.001892215897385!3d52.17969216914519!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x471eccf30d8d5ef7%3A0x23b86eb563b8bbf6!2sGaleria%20Mokot%C3%B3w!5e0!3m2!1spl!2spl!4v1625845673442!5m2!1spl!2spl",
                status:false
            },
            {
                name:"Gdańsk",
                src:"https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2323.5479224445667!2d18.598495815962302!3d54.38263640428397!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x46fd74ea79e3fd01%3A0x3cd7c4eada1b8ed4!2sGaleria%20Ba%C5%82tycka!5e0!3m2!1spl!2spl!4v1625845692140!5m2!1spl!2spl",
                status:false
            }
        ])

        const clearAll = () => {
            cities.value.forEach(city => {
                city.status = false;
            })

        }

        const showMap = (index) => {
            clearAll();
            cities.value[index].status = true;
            console.log(cities);
        }

        return {cities, showMap}
    }
    
}
</script>
<style lang="scss" scoped>
@import '../assets/scss/style.scss';

.contactWrapper{
    & > .sectionContent{
        display:flex;
        flex-direction: column;

        & > .title{
            grid-area: title;
        }

        & > .contactContainer {
            grid-area: contactContainer;
            display:flex;
            flex-direction: column;
            align-items: center;
            font-size:$medium-font;

            & > h3 {
                margin: 5px;
            }
        }

        & > .mapsControls{
            display:flex;
            margin: 40px 0;

            & > .buttonsContainer{
                height:100%;
                grid-area: buttonsContainer;
                display:flex;
                flex-direction: column;
                justify-content: center;

                & > .buttons{
                    // margin: 0 20px
                    padding: 0 70px;

                    & > button {
                        width: 100%;
                        margin:30px;
                        padding: 15px 10px;
                        border: 2px solid black;
                        background-color:transparent;
                        border-radius: 0 15px 0 15px;
                        cursor: pointer;
                        transition: 300ms ease-in-out;

                        &:hover{
                            transform:scale(1.1);
                            background-color: $color-dark;
                            color:$color-white;
                            transition: 300ms;
                            box-shadow: $light-shadow-box;
                        }
                    }
                }
            }

            & > .mapContainer{
                height:fit-content;
                grid-area: mapContainer;
            }
        }
    }
}

</style>
