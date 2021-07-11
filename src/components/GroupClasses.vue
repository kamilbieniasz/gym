<template>
  <section class="groupClassesWrapper">
        <h2>Zajęcia grupowe</h2>
        <div class="gridContainer">
            <GroupClassesItem image="/images/groupClasses/zumba.jpg" title="Zumba"/>
            <GroupClassesItem image="/images/groupClasses/joga.jpg" title="Joga"/>
            <GroupClassesItem image="/images/groupClasses/kettlebell.jpg" title="Kettlebell"/>
            <GroupClassesItem image="/images/groupClasses/cardio.jpg" title="Cardio"/>
            <GroupClassesItem image="/images/groupClasses/crunches.jpg" title="Płaski brzuch"/>
            <GroupClassesItem image="/images/groupClasses/tbc.jpg" title="TBC"/>
            <GroupClassesItem image="/images/groupClasses/stretching.jpg" title="Stretching"/>
            <GroupClassesItem image="/images/groupClasses/trx.jpg" title="TRX"/>
            <GroupClassesItem image="/images/groupClasses/boxing.jpg" title="Boks"/>
            <GroupClassesItem image="/images/groupClasses/step.jpg" title="Power step"/>
            <GroupClassesItem image="/images/groupClasses/kickboxing.jpg" title="Kick boxing"/>
            <GroupClassesItem image="/images/groupClasses/crossfit.jpg" title="Crossfit"/>
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
    display:flex;

    & > .gridContainer{
        width:100%;
        height:100%;
        display:grid;
        grid-template-columns: repeat(4, 1fr);
    }
}

</style>
