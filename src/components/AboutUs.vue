<template>
  <section id="aboutUs" class="aboutUsWrapper">
    <h2 class="title">O nas</h2>

    <div class="content">
      <div class="description">
        <h2>Lorem ipsum</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur omnis dicta voluptatibus optio
          voluptates sit rerum quos commodi, dolor vel unde quas officiis ratione eaque voluptas, beatae totam
          reiciendis excepturi.
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur omnis dicta voluptatibus optio voluptates
          sit rerum quos commodi, dolor vel unde quas officiis ratione eaque voluptas, beatae totam reiciendis
          excepturi.
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur omnis dicta voluptatibus optio voluptates
          sit rerum quos commodi, dolor vel unde quas officiis ratione eaque voluptas, beatae totam reiciendis
          excepturi.
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur omnis dicta voluptatibus optio voluptates
          sit rerum quos commodi, dolor vel unde quas officiis ratione eaque voluptas, beatae totam reiciendis
          excepturi.
        </p>
      </div>
      <div class="image-wrapper">
<!--        <img src="../assets/images/aboutUs/main.webp" alt="Description image"/>-->
      </div>
      <GridItemLayer
          class="access"
          title="Dostęp 24/7"
          description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium cumque harum tempora tenetur architecto facilis quas iste facere dolores reiciendis! Quidem reprehenderit voluptatibus omnis, consectetur vero soluta officiis architecto eius!"
          bgImageJpg="/images/aboutUs/1.jpg"
          bgImageWebp="/images/aboutUs/1.webp"/>

      <GridItemLayer
          class="pass"
          title="Karnet szyty na miarę"
          description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium cumque harum tempora tenetur architecto facilis quas iste facere dolores reiciendis! Quidem reprehenderit voluptatibus omnis, consectetur vero soluta officiis architecto eius!"
          bgImageJpg="/images/aboutUs/2.jpg"
          bgImageWebp="/images/aboutUs/2.webp"/>

      <GridItemLayer
          class="equipment"
          title="Najlepszy sprzęt"
          description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium cumque harum tempora tenetur architecto facilis quas iste facere dolores reiciendis! Quidem reprehenderit voluptatibus omnis, consectetur vero soluta officiis architecto eius!"
          bgImageJpg="/images/aboutUs/3.jpg"
          bgImageWebp="/images/aboutUs/3.webp"/>

      <GridItemLayer
          class="trainingPlan"
          title="Plan treningowy"
          description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium cumque harum tempora tenetur architecto facilis quas iste facere dolores reiciendis! Quidem reprehenderit voluptatibus omnis, consectetur vero soluta officiis architecto eius!"
          bgImageJpg="/images/aboutUs/4.jpg"
          bgImageWebp="/images/aboutUs/4.webp"/>
    </div>
  </section>
</template>
<script>
import GridItemLayer from './GridItemLayer';

export default {
  name: 'AboutUs',
  components: {
    GridItemLayer
  }

}
</script>
<style lang="scss" scoped>
@import "../assets/scss/style.scss";


.aboutUsWrapper {
  width: 100%;
  height: 100%;

  & > div.content {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-areas: "description"
                         "image"
                         "access"
                         "pass"
                         "equipment"
                         "trainingPlan";
    width: 100%;
    height: 100%;
    grid-gap: 1rem;
    padding: 0.5rem;

    @include respond-to(min-width, 568px) {
      grid-template-columns: 1fr 1fr;
      grid-template-areas: "description description"
                           "image image"
                           "access pass"
                           "equipment trainingPlan";
    }

    @include respond-to(min-width, 768px) {
      grid-template-columns: 1fr 1fr;
      grid-template-areas: "description image"
                           "access pass"
                           "equipment trainingPlan";
    }

    @include respond-to(min-width, 1024px) {
      grid-template-columns: 1fr 1fr 1fr 1fr;
      grid-template-areas: "description description image image"
                           "access pass equipment trainingPlan";
    }

    & > div.description {
      grid-area: description;
    }

    & > div.image-wrapper {
      grid-area: image;
      background-image: url("../assets/images/aboutUs/main.webp");
      background-size: cover;
      background-position: center;
      min-height: $minTileHeight;
    }

    & > div.access {
      grid-area: access;
    }

    & > div.pass {
      grid-area: pass;
    }

    & > div.equipment {
      grid-area: equipment;
    }

    & > div.trainingPlan {
      grid-area: trainingPlan;
    }

    & > div.access,
    & > div.pass,
    & > div.equipment,
    & > div.trainingPlan {
      min-height: $minTileHeight;
    }
  }

  & > .descriptionContainer {
    width: 100%;
    display: flex;
    justify-content: center;
    gap: 5px;

    & > .description {
      width: 50%;
      display: flex;
      flex-direction: column;
      justify-content: space-evenly;
      //background-color: $color-dark;
      color: $color-white;
      background: rgb(107, 22, 22);
      background: linear-gradient(323deg, rgba(107, 22, 22, 1) 0%, rgba(73, 27, 27, 1) 10%, rgba(54, 30, 30, 1) 20%, rgba(33, 33, 33, 1) 100%);

      @include respond-to(max-width, 768px) {
        width: 100%;
      }

      & > h2 {
        font-size: $bigger-font;
        text-align: center;
      }

      & > p {
        font-size: $medium-font;
        padding: 0 1rem;
      }
    }

    & > picture {
      width: 50%;

      @include respond-to(max-width, 768px) {
        display: none;
      }

      & > img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center;
      }
    }
  }
}

</style>
