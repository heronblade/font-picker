<template>
  <section class="main">
    <div class="text">
      <input v-model="message" type="text" placeholder="try me">
    </div>
    <colorPicker
      v-on:handleColorClick="handleColorClick"
    ></colorPicker>
    <div v-for="font in fonts" v-bind:key="font.name" class="font">
      <p>{{font.name}}</p>
      <p v-bind:style="{
      fontFamily: font.name,
      fontSize: fontSize + 'px',
      color: activeColor }">{{message}}</p>
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
  },
};
</script>
