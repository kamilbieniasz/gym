<template>
  <section class="groupClassesWrapper">
      <div class="sectionContent">
        <h2 class="title">Zajęcia grupowe</h2>
        <div class="gridContainer">
            <GroupClassesItem image="/images/groupClasses/zumba.jpg" title="Zumba"/>
            <GroupClassesItem image="/images/groupClasses/joga.jpg" title="Joga"/>
            <GroupClassesItem image="/images/groupClasses/kettlebell.jpg" title="Kettlebell"/>
            <GroupClassesItem image="/images/groupClasses/cardio.jpg" title="Cardio"/>
            <GroupClassesItem v-if="showAdditionalClasses" image="/images/groupClasses/crunches.jpg" title="Płaski brzuch"/>
            <GroupClassesItem v-if="showAdditionalClasses" image="/images/groupClasses/tbc.jpg" title="TBC"/>
            <GroupClassesItem v-if="showAdditionalClasses" image="/images/groupClasses/stretching.jpg" title="Stretching"/>
            <GroupClassesItem v-if="showAdditionalClasses" image="/images/groupClasses/trx.jpg" title="TRX"/>
            <GroupClassesItem v-if="showAdditionalClasses" image="/images/groupClasses/boxing.jpg" title="Boks"/>
            <GroupClassesItem v-if="showAdditionalClasses" image="/images/groupClasses/step.jpg" title="Power step"/>
            <GroupClassesItem v-if="showAdditionalClasses" image="/images/groupClasses/kickboxing.jpg" title="Kick boxing"/>
            <GroupClassesItem v-if="showAdditionalClasses" image="/images/groupClasses/crossfit.jpg" title="Crossfit"/>
        </div>
      </div>
      <button class="showMoreBtn" @click="showMore">{{btnText}}</button>
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
    height:fit-content;

    & > .sectionContent{
        height:100%;

        & > .gridContainer{
            display:grid;
            grid-template-columns: repeat(4, 1fr);
            grid-gap:60px;
        }
    }
        & > .showMoreBtn{
            margin:30px;
            padding: 10px 15px;
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

</style>
