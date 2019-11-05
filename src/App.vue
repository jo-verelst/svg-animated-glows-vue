<template>
  <div id="app">
    <section class="decision-banner" :class="roomClass">
      <div class="container">
        <h1>{{header}}</h1>
        <div class="button-row">
          <a @click="switchRoom('indoor')">Indoor</a>
          <a @click="switchRoom('outdoor')">Outdoor</a>
          <a @click="switchRoom('livingRoom')">Living room</a>
          <a @click="switchRoom('lightbulbs')">Lightbulbs</a>
        </div>
      </div>
      <Glow class="glow-1" startColor="#00FFFF" stopColor="#FFFF00" />
      <Glow class="glow-2" startColor="#FF00FF" stopColor="#00FFFF" />
      <Glow class="glow-3" startColor="#FFFFFF" stopColor="#FFFF00" />
    </section>
    <section class="products">
      <div class="container">
        <div class="product-card"></div>
        <div class="product-card"></div>
        <div class="product-card"></div>
        <div class="product-card"></div>
        <div class="product-card"></div>
        <div class="product-card"></div>
        <div class="product-card"></div>
        <div class="product-card"></div>
        <div class="product-card"></div>
      </div>
    </section>
  </div>
</template>

<script>
import Glow from "./components/Glow.vue";

export default {
  name: "app",
  components: {
    Glow
  },
  data() {
    return {
      roomClass: '',
      header: '',
      productPresets: {
        indoor: {
          header: 'Indoor',
          class: 'indoor'
        },
        outdoor: {
          header: 'Outdoor',
          class: 'outdoor'
        },
        livingRoom: {
          header: 'Living Room',
          class: 'living-room'
        },
        lightbulbs: {
          header: 'Lightbulbs',
          class: 'lightbulbs'
        }
      }
    };
  },
  mounted() {
    this.roomClass = this.productPresets['indoor'].class;
    this.header = this.productPresets['indoor'].header;
  },
  methods: {
    switchRoom(productPresetKey) {
      this.roomClass = this.productPresets[productPresetKey].class;
      this.header = this.productPresets[productPresetKey].header;
    }
  }
};
</script>
<style lang="scss">
#app {}
</style>
