<template>
  <div>
    <vue-select-image
      :dataImages="dataImages"
      @onselectimage="onSelectImage"
      :is-multiple="true"
      :selectedImages="initialSelected"
      @onselectmultipleimage="onSelectMultipleImage"
    >
    </vue-select-image>

    <div v-if="selectedImages.length > 0">
      <div>{{ selectedImages.length }} images selected:</div>
      <div v-for="(image, idx) in selectedImages" :key="idx">
        {{ image.alt }}
      </div>
    </div>
  </div>
</template>

<script>
import VueSelectImage from "vue-select-image";
import "vue-select-image/dist/vue-select-image.css";

export default {
  name: "SelectImage",
  data() {
    return {
      selectedImages: [],
      initialSelected: [],
      dataImages: [
        {
          id: "1",
          src: "https://unsplash.it/150?random=1",
          alt: "nightprogrammer.com image 1",
        },
        {
          id: "2",
          src: "https://unsplash.it/150?random=2",
          alt: "nightprogrammer.com image 2",
        },
        {
          id: "3",
          src: "https://unsplash.it/150?random=3",
          alt: "nightprogrammer.com image 3",
        },
        {
          id: "4",
          src: "https://unsplash.it/150?random=4",
          alt: "nightprogrammer.com image 4",
        },
        {
          id: "5",
          src: "https://unsplash.it/150?random=5",
          alt: "nightprogrammer.com image 5",
        },
        {
          id: "6",
          src: "https://unsplash.it/150?random=6",
          alt: "nightprogrammer.com image 6",
        },
      ],
    };
  },
  methods: {
    onSelectImage(img) {
      alert(`Selected image: ${img.alt}`);
    },
    onSelectMultipleImage(images) {
      this.selectedImages = images;
      //alert("multiple selected");
    },
  },
  components: {
    VueSelectImage,
  },
};
</script>
