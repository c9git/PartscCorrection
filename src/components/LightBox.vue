<template>
  <div class="lighitbox">
    <div v-for="(image, index) in images" :key="image.id" class="thumbnail">
      <img v-lazy="image.src" @click="openImg(index)" />
    </div>
    <ImageLightBox ref="lightbox" :media="images" :showLightBox="false" :showThumbs="false"></ImageLightBox>
  </div>
</template>

<script>
import ImageLightBox from "vue-image-lightbox";
export default {
  name: "LightBox",
  components: {
    ImageLightBox
  },
  data() {
    return {
      images: [
        {
          src: "https://www.pakutaso.com/shared/img/thumb/HNIMGL8843_TP_V.jpg",
          id: 1
        },
        {
          src:
            "https://www.pakutaso.com/shared/img/thumb/214hariIMGL9360_TP_V.jpg",
          id: 2
        },
        {
          src: "https://www.pakutaso.com/shared/img/thumb/HNIMGL9599_TP_V.jpg",
          id: 3
        },
        {
          src:
            "https://www.pakutaso.com/shared/img/thumb/harinezumiIMGL8714_TP_V.jpg",
          id: 4
        },
        {
          src:
            "https://www.pakutaso.com/shared/img/thumb/harinezumiIMGL9392_TP_V.jpg",
          id: 5
        },
        {
          src:
            "https://www.pakutaso.com/shared/img/thumb/harinezumiIMGL0203_TP_V.jpg",
          id: 6
        },
        {
          src:
            "https://www.pakutaso.com/shared/img/thumb/KAZUHIRO171013186_TP_V.jpg",
          id: 7
        },
        {
          src:
            "https://www.pakutaso.com/shared/img/thumb/KAZUHIRO171013331_TP_V.jpg",
          id: 8
        },
        {
          src:
            "https://www.pakutaso.com/shared/img/thumb/hedgehogIMGL8983_TP_V.jpg",
          id: 9
        },
        {
          src: "https://www.pakutaso.com/shared/img/thumb/HNIMGL8586_TP_V.jpg",
          id: 10
        }
      ]
    };
  },
  methods: {
    openImg(index) {
      this.$refs.lightbox.showImage(index);
    }
  }
};
</script>

<style lang="scss">
@import "~vue-image-lightbox/dist/vue-image-lightbox.min.css";


.lighitbox {
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    align-items: center;
  }
  .thumbnail {
    width: calc(100%/3);

    @media screen and (min-width: 1024px){
    width: calc(100%/5);
    }
    &:hover {
      opacity: 0.7;
      cursor: pointer;
    }
    img {
      width: 100%;
    }
  }


</style>
