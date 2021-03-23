<template>
  <div id="app">
    <ul>
      <li :key="index" v-for="(image,index) in listImage">
        <img :src="image.src" alt="" @click="openGallery(index)"/>
      </li>
    </ul>
    <Gallery :images="listImage" ref="imagebox" :show-caption="true" :show-image-box="false"></Gallery>
  </div>
</template>

<script>
import Gallery from "./components/Gallery.vue";

export default {
  name: "app",
  components: {
    Gallery
  },
  data() {
    return {
      listImage: []
    };
  },
  mounted() {
    this.loadImages();
  },
  methods: {
    async loadImages() {
      return (this.listImage = [
        {
          src: require("@/assets/images/slide01.jpg"),
          caption: "Slide01",
          galleryType: "image"
        },
        {
          src: require("@/assets/images/slide02.jpg"),
          caption: "Slide02",
          galleryType: "image"
        },
        {
          src: require("@/assets/images/slide03.jpg"),
          caption: "Slide03",
          galleryType: "image"
        },
        {
          src: require("@/assets/images/slide04.jpg"),
          caption: "Slide04",
          galleryType: "image"
        },
        {
          src: require("@/assets/images/slide05.jpg"),
          caption: "",
          galleryType: "image"
        },
        {
          src: require("@/assets/images/slide06.jpg"),
          caption: "",
          galleryType: "image"
        },
        {
          src: require("@/assets/images/slide07.jpg"),
          caption: "",
          galleryType: "image"
        },
        {
          src: require("@/assets/images/slide08.jpg"),
          caption: "",
          galleryType: "image"
        },
        {
          src: require("@/assets/images/slide01.jpg"), // thumbnail of video
          videoURL: "https://www.youtube.com/embed/Z3aZABXrAeI",
          caption: "",
          galleryType: "video"
        }
      ]);
    },
    openGallery(index) {
      this.$refs.imagebox.showImage(index);
    }
  }
};
</script>

<style>
ul li {
  list-style-type: none;
  display: inline-block;
  margin: 0 5px;
}
li img {
  height: 100px;
}
</style>
