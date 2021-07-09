<template>
    <section class="aboutUsWrapper">
        <div class="sectionContent">
            <h2 class="title">O nas</h2>
            <div class="gridContainer">
                <CardItem 
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
                message="Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita odio eum fugit, sit eaque distinctio commodi neque cum nesciunt architecto vero recusandae sequi corrupti fugiat quos veritatis repudiandae dignissimos animi." />
            </div>
        </div>
    </section>
</template>
<script>
import CardItem from './CardItem';

export default {
    name: 'AboutUs',
    components: {
        CardItem,
    }
    
}
</script>
<style lang="scss" scoped>
@import "../assets/scss/style.scss";


.aboutUsWrapper{

    .sectionContent{

    & > .title {
        font-size:$biggest-font;
    }

    & > .gridContainer{
        display:grid;
        grid-gap:60px;
        grid-template-columns: repeat(2, 1fr);
        justify-items: center;
        align-items: center;
        text-align: center;
    }
    }
}
    
</style>
