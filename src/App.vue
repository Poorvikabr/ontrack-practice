<template>
  <div id="app">
    <h1>Hello, here!</h1>
    <p>{{ message }}</p>
    
    <button @click="toggleImage">{{ imageVisible ? 'Hide Image' : 'Show Image' }}</button>
    
    <img v-if="imageVisible" 
         src="https://www.pocketwanderings.com/wp-content/uploads/2021/01/Spiez-1.jpg"
         :style="{ width: '500px', height: '500px' }">
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: '------welcome ------',
      imageVisible: false 
    };
  },
  methods: {
    toggleImage() {
      this.message = this.imageVisible ? 'Image hidden!' : 'You clicked the button!';
      this.imageVisible = !this.imageVisible; 
    }
  }
}
</script>

<style>
#app {
  font-family: Trebuchet MS, sans-serif;
  text-align: center;
  color: #76032b;
  margin-top: 50px;
}
</style>
