<template>
    <section class="aboutUsWrapper">
        <h2 class="title">O nas</h2>
        <div class="gridContainer">
            <AboutUsItem 
            title="Dostęp 24/7" 
            icon="clock"
            message="Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita odio eum fugit, sit eaque distinctio commodi neque cum nesciunt architecto vero recusandae sequi corrupti fugiat quos veritatis repudiandae dignissimos animi." />
            <AboutUsItem 
            title="Karnet szyty na miare" 
            icon="calendar" 
            message="Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita odio eum fugit, sit eaque distinctio commodi neque cum nesciunt architecto vero recusandae sequi corrupti fugiat quos veritatis repudiandae dignissimos animi." />
            <AboutUsItem 
            title="Najlepszy sprzęt" 
            icon="dumbbell" 
            message="Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita odio eum fugit, sit eaque distinctio commodi neque cum nesciunt architecto vero recusandae sequi corrupti fugiat quos veritatis repudiandae dignissimos animi." />
            <AboutUsItem 
            title="Plan treningowy" 
            icon="clipboard" 
            message="Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita odio eum fugit, sit eaque distinctio commodi neque cum nesciunt architecto vero recusandae sequi corrupti fugiat quos veritatis repudiandae dignissimos animi." />
        </div>
    </section>
</template>
<script>
import AboutUsItem from './AboutUsItem';

export default {
    name: 'AboutUs',
    components: {
        AboutUsItem,
    }
    
}
</script>
<style lang="scss" scoped>
@import "../assets/scss/style.scss";


.aboutUsWrapper{
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;

    & > .title {
        font-size:$biggest-font;
    }

    & > .gridContainer{
        display:grid;
        grid-gap:60px;
        grid-template-columns: repeat(2, 1fr);
    }
}
    
</style>