<template>
  <div id="app">
    <h1>Welcome!</h1>
    <p>{{ message }}</p>

    <button :style="{ backgroundColor: 'red' }" @click="toggleImage">
      {{ imageVisible ? "Hide Image" : "Show Image" }}
    </button>

    <div>
      <img
        v-if="imageVisible"
        :src="images[currentImageIndex]"
        @click="changeImage"
        :style="{ width: '300px', height: '200px' }"
      />
      <!-- Add desired width and height -->
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "Click the button to toggle the image",
      imageVisible: false,
      images: [
        "https://www.pocketwanderings.com/wp-content/uploads/2021/01/Spiez-1.jpg",
        "https://i.pinimg.com/originals/32/14/3b/32143bf64ff46d94b4a8f9a81cec176f.jpg",
        "https://wallpapercave.com/wp/BAzd38d.jpg",
        "https://jooinn.com/images/a-beach-and-ocean-sunset.jpg",
      ],
      currentImageIndex: 0,
    };
  },
  methods: {
    toggleImage() {
      this.message = this.imageVisible
        ? "Image is now hidden"
        : "Image is now visible";
      this.imageVisible = !this.imageVisible;
    },
    changeImage() {
      this.currentImageIndex =
        (this.currentImageIndex + 1) % this.images.length;
      console.log("Current Image Index:", this.currentImageIndex);
    },
  },
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  text-align: center;
  padding: 20px;
}

button {
  margin-top: 10px;
  padding: 8px 16px;
  background-color: #4400ff;
  color: white;
  border: none;
  border-radius: 3px;
  cursor: pointer;
}
img {
  margin-top: 10px;
  max-width: 100%;
  height: auto;
  cursor: pointer;
}
</style>
