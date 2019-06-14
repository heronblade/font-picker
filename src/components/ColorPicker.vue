<template>
  <div class="color-picker">
    <div class="color"
         v-for="color in colors"
         v-bind:key="color"
         v-bind:style="{ backgroundColor: color, }"
         v-on:click="colorClick(color)"
    ></div>
  </div>
</template>

<script>
export default {
  name: 'ColorPicker',
  data() {
    return {
      colors: [
        'rgb(10, 15, 23)',
        'rgb(56, 56, 56)',
        'rgb(24, 84, 23)',
        'rgb(26, 57, 99)',
        'rgb(64, 32, 85)',
        'rgb(222, 158, 40)',
        'rgb(224, 96, 15)',
        'rgb(148, 29, 31)',
        'rgb(73, 43, 35)',
        'rgb(4, 4, 4)'],
    };
  },
  methods: {
    colorClick(color) {
      this.$emit('handleColorClick', color);
    },
  },
};
</script>
