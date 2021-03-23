# VueJS Image and Video Gallery
A simple, highly customisable responsive and customizable image and video gallery, carousel and lightbox, optimized for both mobile and desktop web browsers.

## Installing
```
npm install --save awesome_vue_gallery vue-lazyload
```

# Usage
Step 1: Import vue-lazyload in your project At your entry point in `main.js`
```
import Vue from 'vue'
import VueLazyLoad from 'vue-lazyload'
...
Vue.use(VueLazyLoad)
```
Step 2: import `AwesomeVueGallery` in our component
``` 
import AwesomeVueGallery from 'awesome_vue_gallery';
export default {
  name: 'App',
  components: {
    AwesomeVueGallery
  }
}

```
Step 3: Load default values to the component
```
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
          src: 'https://user-images.githubusercontent.com/3702438/112178105-864cff80-8c1f-11eb-83d1-9581078cdf8e.jpg',
          caption: "Image 4",
          galleryType: 'image'
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
          caption: "",
          galleryType: 'video'
        }
      ],
      showCaption: false,
      showImageBox: false
    }
}
  
```
Step 4: Place the Gallery component inside the template
```
<template>
  <div id="app">
    <h1>Display from Server file path</h1>
    <ul>
      <li :key="index" v-for="(image,index) in images">
        <img :src="image.src" alt="" @click="openGallery(index)" />
      </li>
    </ul>
    <AwesomeVueGallery :images="images" ref="imagebox" :show-caption="showCaption" :show-image-box="showImageBox" />
  </div>
</template>
```
Step 5: Add Open Imagebox Gallery view
```
methods: {
   openGallery(index) {
      this.$refs.imagebox.showImage(index);
   }
}
```

### Compiles and hot-reloads for development
```
npm run serve
```
# Screenshot
![Vue Gallery](https://user-images.githubusercontent.com/3702438/112180262-661e4000-8c21-11eb-8e1c-33a42e605c09.jpg)

# Demo

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```
