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
          src: "https://img.youtube.com/vi/JGwWNGJdvx8/mqdefault.jpg",
          videoURL: "https://www.youtube.com/embed/JGwWNGJdvx8",
          caption: "Video 1",
          galleryType: "video",
        },
        {
          src: require("@/assets/images/slide02.jpg"),
          caption: "Slide02",
          galleryType: "image"
        },
        {
          src: "https://user-images.githubusercontent.com/3702438/112178912-2acf4180-8c20-11eb-8700-385274d70357.jpg",
          videoURL: "https://www.youtube.com/embed/Z3aZABXrAeI",
          caption: "Video 2",
          galleryType: "video",
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
