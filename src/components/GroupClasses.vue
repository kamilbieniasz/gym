<template>
  <section class="groupClassesWrapper">
        <h2 class="title">Zajęcia grupowe</h2>
        <div class="gridContainer">
            <GroupClassesItem bgImageJpg="/images/groupClasses/zumba.jpg" bgImageWebp="/images/groupClasses/zumba.webp" title="Zumba"/>
            <GroupClassesItem bgImageJpg="/images/groupClasses/joga.jpg" bgImageWebp="/images/groupClasses/joga.webp" title="Joga"/>
            <GroupClassesItem bgImageJpg="/images/groupClasses/kettlebell.jpg" bgImageWebp="/images/groupClasses/kettlebell.webp" title="Kettlebell"/>
            <GroupClassesItem bgImageJpg="/images/groupClasses/cardio.jpg" bgImageWebp="/images/groupClasses/cardio.webp" title="Cardio"/>
            <GroupClassesItem bgImageJpg="/images/groupClasses/crunches.jpg" bgImageWebp="/images/groupClasses/crunches.webp" title="Płaski brzuch"/>
            <GroupClassesItem bgImageJpg="/images/groupClasses/tbc.jpg" bgImageWebp="/images/groupClasses/tbc.webp" title="TBC"/>
            <GroupClassesItem bgImageJpg="/images/groupClasses/stretching.jpg" bgImageWebp="/images/groupClasses/stretching.webp" title="Stretching"/>
            <GroupClassesItem bgImageJpg="/images/groupClasses/trx.jpg" bgImageWebp="/images/groupClasses/trx.webp" title="TRX"/>
            <GroupClassesItem bgImageJpg="/images/groupClasses/boxing.jpg" bgImageWebp="/images/groupClasses/boxing.webp" title="Boks"/>
            <GroupClassesItem bgImageJpg="/images/groupClasses/step.jpg" bgImageWebp="/images/groupClasses/step.webp" title="Power step"/>
            <GroupClassesItem bgImageJpg="/images/groupClasses/kickboxing.jpg" bgImageWebp="/images/groupClasses/kickboxing.webp" title="Kick boxing"/>
            <GroupClassesItem bgImageJpg="/images/groupClasses/crossfit.jpg" bgImageWebp="/images/groupClasses/crossfit.webp" title="Crossfit"/>
        </div>
      <!-- <button class="showMoreBtn" @click="showMore">{{btnText}}</button> -->
  </section>  
</template>
<script>
import { ref } from 'vue';
import GroupClassesItem from './GroupClassesItem.vue'
export default {
    name: "GroupClasses",
    components: {
        GroupClassesItem
    },
    setup() {
        const showAdditionalClasses = ref(false);
        const btnText = ref("Pokaż więcej");

        const showMore = () => {
            showAdditionalClasses.value = !showAdditionalClasses.value;
            btnText.value = btnText.value === "Pokaż więcej" ? "Pokaż mniej" : "Pokaż więcej";
        }

        return {showAdditionalClasses, btnText, showMore};
    }

}
</script>
<style lang="scss" scoped>
@import '../assets/scss/style.scss';
.groupClassesWrapper{
    width: 100vw;
    display:flex;

    & > .gridContainer{
        width:100%;
        height:100%;
        display:grid;
        grid-template-columns: repeat(4, 1fr);
        grid-gap:10px;

        @include respond-to(max-width, 1024px){
            grid-template-columns: repeat(3, 1fr);
        }

        @include respond-to(max-width, 768px){
            grid-template-columns: repeat(2, 1fr);
        }
    }
}

</style>
