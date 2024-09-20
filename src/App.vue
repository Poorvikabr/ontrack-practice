<template>
  <div id="app">
    <h1>Welcome!</h1>
    <p>{{ message }}</p>

    <button :style="{ backgroundColor: 'green' }" @click="toggleImage">
      {{ imageVisible ? "Hide Images" : "Show Images" }}
    </button>

    <div v-if="imageVisible">
      <img
        v-for="(image, index) in images"
        :key="index"
        :src="image"
        @click="changeImage(index)"
        :style="{ width: '300px', height: '200px', margin: '10px' }"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "Click the button to toggle the images",
      imageVisible: false,
      images: [
        "https://www.pocketwanderings.com/wp-content/uploads/2021/01/Spiez-1.jpg",
        "https://i.pinimg.com/originals/32/14/3b/32143bf64ff46d94b4a8f9a81cec176f.jpg",
        "https://wallpapercave.com/wp/BAzd38d.jpg",
        "https://jooinn.com/images/a-beach-and-ocean-sunset.jpg",
      ],
    };
  },
  methods: {
    toggleImage() {
      this.imageVisible = !this.imageVisible;
      this.message = this.imageVisible ? "Images are now visible" : "Images are now hidden";
    },
    changeImage(index) {
      console.log("Clicked Image Index:", index);
      
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
  background-color: #8167c7;
  color: rgb(200, 199, 192);
  border: none;
  border-radius: 3px;
  cursor: pointer;
}
img {
  cursor: pointer;
}
</style>
