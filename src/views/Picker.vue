<template>
  <section class="picker">
    <div class="picker__section">
      <div class="picker__instructions">Enter Name or Text</div>
      <input v-model="message" type="search" placeholder="Name or Text Here">
    </div>
    <div class="picker__section">
      <div class="picker__instructions">Choose a color</div>
      <colorPicker
        v-on:handleColorClick="handleColorClick"
      ></colorPicker>
    </div>
    <div class="picker__section">
      <div class="picker__instructions">Choose a font</div>
      <div v-for="font in fonts" v-bind:key="font.name" class="font">
        <p>{{font.name}}</p>
        <p v-bind:style="{
      fontFamily: font.name,
      fontSize: fontSize + 'px',
      color: activeColor }">{{message}}</p>
        <button v-on:click="handleFontClick(font.name)">Pick Font</button>
      </div>
    </div>
  </section>
</template>

<script>
import colorPicker from '../components/ColorPicker.vue';

export default {
  name: 'picker',
  components: {
    colorPicker,
  },
  data() {
    return {
      activeColor: 'black',
      fontSize: 30,
      fonts: [
        {
          name: 'Righteous',
        },
        {
          name: 'Open Sans Condensed',
        },
        {
          name: 'Lobster',
        },
        {
          name: 'Pacifico',
        },
        {
          name: 'Shadows into Light',
        },
        {
          name: 'Amatic',
        },
      ],
      message: '',
    };
  },
  methods: {
    handleColorClick(color) {
      this.activeColor = color;
    },
    handleFontClick(font) {
      console.log(font);
    }
  },
};
</script>
