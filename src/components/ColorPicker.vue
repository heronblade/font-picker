<template>
  <div class="color-picker">
    <div class="color"
         v-for="(color, index) in colors"
         v-bind:key="color"
         v-bind:style="{ backgroundColor: color, borderColor: borderColors[index] }"
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
        'rgba(10, 15, 23, 1)',
        'rgba(56, 56, 56, 1)',
        'rgba(24, 84, 23, 1)',
        'rgba(26, 57, 99, 1)',
        'rgba(64, 32, 85, 1)',
        'rgba(222, 158, 40, 1)',
        'rgba(224, 96, 15, 1)',
        'rgba(148, 29, 31, 1)',
        'rgba(73, 43, 35, 1)',
        'rgba(4, 4, 4, 1)'
      ],
    };
  },
  methods: {
    colorClick(color) {
      this.$emit('handleColorClick', color);
    },
  },
  computed: {
    borderColors: function() {
      return this.colors
        .map((color) => {
          const splitColor = color.split(',');
          splitColor.pop();
          splitColor.push(' 0.8)');
          return splitColor.join(',');
        });
    },
  },
};
</script>
