<template>
  <div id="app">
    <ul>
      <li :key="index" v-for="(image,index) in images">
        <img :src="image.src" alt="" @click="openGallery(index)" />
      </li>
    </ul>
    <AwesomeVueGallery :images="images" ref="imagebox" :show-caption="showCaption" :show-image-box="showImageBox" />
  </div>
</template>

<script>
import AwesomeVueGallery from 'awesome_vue_gallery';
export default {
  name: 'App',
  components: {
    AwesomeVueGallery
  },
  data() {
    return {
      images: [
        {
          src: 'https://user-images.githubusercontent.com/3702438/112178066-7f25f180-8c1f-11eb-9821-7ad6cb7653ad.jpg',
          caption: "Image 1",
          galleryType: 'image'
        },
        {
          src: 'https://user-images.githubusercontent.com/3702438/112178096-84833c00-8c1f-11eb-8d94-f56749391a7f.jpg',
          caption: "Image 2",
          galleryType: 'image'
        },
        {
          src: 'https://user-images.githubusercontent.com/3702438/112178102-85b46900-8c1f-11eb-8081-9313bf51bafc.jpg',
          caption: "Image 3",
          galleryType: 'image'
        },
        {
          src: 'https://img.youtube.com/vi/JGwWNGJdvx8/mqdefault.jpg',
          videoURL: 'https://www.youtube.com/embed/JGwWNGJdvx8',
          caption: "Video 1",
          galleryType: 'video'
        },
        {
          src: 'https://user-images.githubusercontent.com/3702438/112178106-864cff80-8c1f-11eb-874b-e8a814a48cea.jpg',
          caption: "Image 5",
          galleryType: 'image'
        },
        {
          src: 'https://user-images.githubusercontent.com/3702438/112178108-86e59600-8c1f-11eb-8212-7fc96e5e7c68.jpg',
          caption: "Image 6",
          galleryType: 'image'
        },
        {
          src: 'https://user-images.githubusercontent.com/3702438/112178111-877e2c80-8c1f-11eb-964d-1de46bbe21f0.jpg',
          caption: "Image 7",
          galleryType: 'image'
        },
        {
          src: 'https://user-images.githubusercontent.com/3702438/112178115-877e2c80-8c1f-11eb-8237-773872edd951.jpg',
          caption: "Image 8",
          galleryType: 'image'
        },
        {
          src: 'https://user-images.githubusercontent.com/3702438/112178912-2acf4180-8c20-11eb-8700-385274d70357.jpg',
          videoURL: 'https://www.youtube.com/embed/Z3aZABXrAeI',
          caption: "Video 2",
          galleryType: 'video'
        }
      ],
      showCaption: false,
      showImageBox: false
    }
  },
  methods: {
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
