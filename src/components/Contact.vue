<template>
    <section class="contactWrapper">
        <h2 class="title">Kontakt</h2>
        <div class="content"> 
            <div class="contact">
                <h3><strong>Telefon: </strong>123 456 789</h3>
                <h3><strong>Email: </strong>gymmaster@gym.pl</h3>
                <h3><strong>Nasza siłownia otwarta jest całodobowo!</strong></h3>
            </div>
            <div class="contactContainer">
                <div class="formContainer">
                    <form>
                        <span>
                            <label for="name">Imię i nazwisko</label>
                            <input id="name" type="text" v-model="messageContent.name" required/>
                        </span>
                        <span>
                            <label for="email">Email</label>
                            <input id="email" type="email" v-model="messageContent.email" required/>
                        </span>
                        <span>
                            <label for="phone">Nr telefonu</label>
                            <input type="tel" pattern="[0-9]{3}-[0-9]{3}-[0-9]{3}" minlength="9" maxlength="9" v-model="messageContent.phone" required/>
                        </span>
                        <span>
                            <label for="message">Wiadomość</label>
                            <textarea id="message" maxlength="400" v-model="messageContent.message" required/>
                        </span>
                    </form>
                    <button @click="sendMessage">Wyślij</button>
                </div>
                <div class="mapsControls">
                    <div class="buttonsContainer">
                        <div class="buttons" v-for="(city, index) in cities" v-bind:key="city">
                            <button @click="showMap(index)">{{city.name}}</button>
                        </div>
                    </div>
                    <div class="mapContainer">
                        <div class="map" v-for="city in cities" v-bind:key="city">
                            <iframe :src="city.src" v-if="city.status" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
                        </div>
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
        ]);

        const messageContent = ref({
            name: "",
            email: "",
            phone: "",
            message: ""
        });

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

        const sendMessage = () => {
            console.log(messageContent);
        }

        return {cities, messageContent, sendMessage, showMap}
    }
    
}
</script>
<style lang="scss" scoped>
@import '../assets/scss/style.scss';

.contactWrapper{
    padding: 0 !important;

        & > .title{
            grid-area: title;
        }

        & > .content{
            width:100%;
            height:100%;
            display:flex;
            flex-direction:column;
            justify-content:space-evenly;
            align-items: center;
            background-color:$color-dark;
            background-image: url('../assets/images/contact/contact.jpg');
            background-image: -webkit-image-set(url('../assets/images/contact/contact.webp')1x );
            background-size:cover;
            background-position:center;
            background-blend-mode: color-burn;
            background-color:rgba($color-dark, 0.6);

            @include respond-to(max-width, 768px){
                padding: 40px 0;
            }

            & > .contact{
                display: flex;

                @include respond-to(max-width, 768px){
                    flex-direction: column;
                }

                & > h3 {
                    padding: 10px 20px;
                    margin: 5px;
                    color:$color-white;
                }
            }

        & > .contactContainer{
            width:100%;
            display:flex;
            justify-content: space-evenly;
            align-items: center;

            @include respond-to(max-width, 768px){
                flex-direction: column-reverse;
            }

            & > .formContainer {
                width:40%;
                height:100%;
                display:flex;
                flex-direction: column;
                justify-content: space-evenly;
                align-items: center;
                font-size:$medium-font;

                @include respond-to(max-width, 1024px){
                    flex-direction: column;
                }

                @include respond-to(max-width, 768px){
                    width: 80%;
                }

                & > form {
                    width: 90%;
                    display:flex;
                    flex-direction: column;

                    & > span{
                        display:flex;
                        flex-direction: column;

                        & > label{
                            color: $color-white;
                        }

                        & > input{
                            height:25px;
                            margin:10px 0;
                        }

                        & > textarea{
                            height: 200px;
                            resize: none;
                        }
                    }
                }               
                & > button{
                    padding: 10px 15px;
                    cursor: pointer;
                    margin: 10px;
                    
                    &:hover{
                        transform:scale(1.1);
                        transition: 300ms;
                        box-shadow: $light-shadow-box;
                    }
                }
            }

            & > .mapsControls{
                width:40%;
                display:flex;
                flex-direction: column;
                margin: 40px 0;

                @include respond-to(max-width, 768px){
                    width: 80%;
                }

                & > .buttonsContainer{
                    width:100%;
                    height:100%;
                    display:flex;
                    justify-content: center;

                    @include respond-to(max-width, 1024px){
                        display:grid;
                        grid-template-columns: repeat(2, 1fr);
                    }

                    & > .buttons{
                        margin:10px;

                        & > button {
                            width: 100%;
                            padding: 10px 15px;
                            border: 2px solid black;
                            background-color:$color-white;
                            cursor: pointer;
                            transition: 300ms ease-in-out;

                            &:hover{
                                transform:scale(1.1);
                                transition: 300ms;
                                box-shadow: $light-shadow-box;
                            }
                        }
                    }
                }

                & > .mapContainer{
                    height:fit-content;

                    & > .map{
                        box-shadow: $shadow-box;
                        -webkit-box-shadow: $shadow-box;
                        background-color:white;

                        & > iframe {
                            width:100%;
                            height:400px;
                        }
                    }
                }
            }
        }
    }
}

</style>
