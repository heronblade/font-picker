<template>
  <section class="picker">
    <div class="picker__section">
      <div class="picker__instructions">Enter Name or Text</div>
      <input v-model="message" type="search" placeholder="Name or Text Here">
    </div>
    <div class="picker__section">
      <div class="picker__instructions">Choose a font</div>
      <div class="font-wrapper">
        <div v-for="font in fonts" v-bind:key="font.name" class="font">
          <p>{{font.name}}</p>
          <p v-bind:style="{
      fontFamily: font.id,
      fontSize: fontSize + 'px',
      color: activeColor }">{{message}}</p>
          <button v-on:click="handleFontClick(font.name)">Pick Font</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'picker',
  data() {
    return {
      activeColor: 'black',
      fontSize: 30,
      fonts: [
        {
          type: 'otf',
          id: 'amastery-script',
          name: 'Swirly',
        }, {
          type: 'otf',
          name: 'Baby Block',
          id: 'arctic',
        }, {
          type: 'otf',
          name: 'Elegant',
          id: 'argentinian-nights-by-kestrel-montes',
        }, {
          type: 'otf',
          name: 'Swoon',
          id: 'aurelia',
        }, {
          type: 'otf',
          name: 'Sweet',
          id: 'bekafonte',
        }, {
          type: 'otf',
          name: 'Fancy Fun',
          id: 'bella-script',
        }, {
          type: 'otf',
          name: 'Bold Fun',
          id: 'bonkers',
        }, {
          type: 'otf',
          name: 'Airy',
          id: 'crystal-sky',
        }, {
          type: 'otf',
          name: 'Majestic',
          id: 'enyssala',
        }, {
          type: 'otf',
          name: 'Tasteful',
          id: 'frutilla-script',
        }, {
          type: 'ttf',
          name: 'Sophisticated',
          id: 'kasting-script',
        }, {
          type: 'otf',
          name: 'Classy',
          id: 'kenstein',
        }, {
          type: 'otf',
          name: 'Cute',
          id: 'king-basil-lite',
        }, {
          type: 'otf',
          name: 'Lovely',
          id: 'legacy',
        }, {
          type: 'ttf',
          name: 'Lego',
          id: 'legothick',
        }, {
          type: 'otf',
          name: 'Wild',
          id: 'lovestone-script',
        }, {
          type: 'ttf',
          name: 'Posh',
          id: 'madina-script-alt',
        }, {
          type: 'otf',
          name: 'Merry',
          id: 'magenta-script',
        }, {
          type: 'otf',
          name: 'Notebook',
          id: 'malina',
        }, {
          type: 'otf',
          name: 'Bold',
          id: 'nexa-bold',
        }, {
          type: 'otf',
          name: 'Trendy',
          id: 'peyton-script',
        }, {
          type: 'otf',
          name: 'Graceful',
          id: 'philosophy-script',
        }, {
          type: 'otf',
          name: 'Playful',
          id: 'playlist-script',
        }, {
          type: 'ttf',
          name: 'Distinguished',
          id: 'questa-whitte',
        }, {
          type: 'otf',
          name: 'Homemade',
          id: 'road-crew-regular',
        }, {
          type: 'otf',
          name: 'Fashion',
          id: 'sakura-regular',
        }, {
          type: 'otf',
          name: 'Chic',
          id: 'shania',
        }, {
          type: 'otf',
          name: 'Floral',
          id: 'vanilla-daisy-pro',
        }, {
          type: 'otf',
          name: 'Adventure',
          id: 'venture',
        }, {
          type: 'ttf',
          name: 'Disney',
          id: 'walto-graph-42',
        }, {
          type: 'otf',
          name: 'Charming',
          id: 'wild-ones-personal-use',
        }, {
          type: 'otf',
          name: 'Delicate',
          id: 'wildflowers',
        }, {
          type: 'otf',
          name: 'Noble',
          id: 'wisdom-scrip',
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
      // Grab the input from the form and put our font name in there
      const labels = document.getElementsByTagName('label');

      for (const label of labels) {
        if (label.innerText === 'Desired Font From Below*') {
          const parent = label.parentElement;
          const parentChildNodes = parent.childNodes;
          for (const pcn of parentChildNodes) {
            const moreKids = pcn.childNodes;
            for (const kid of moreKids) {
              if (kid.nodeName === 'INPUT') {
                kid.value = font;
              }
            }
          }
        }
      }
    },
  },
};
</script>
