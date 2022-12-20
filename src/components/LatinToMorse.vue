<script>
export default {
  data() {
    return {
      latin: '',
    }
  },
  computed: {
    convert() {
      return this.latin.split('').map(char => this.abc(char)).join(' ');
    },
  },
  methods: {
    abc(char) {
      const LatinToMorse = {
        'A': '.-',
        'B': '-...',
        'C': '-.-.',
        'D': '-..',
        'E': '.',
        'F': '..-.',
        'G': '--.',
        'H': '....',
        'I': '..',
        'J': '.---',
        'K': '-.-',
        'L': '.-..',
        'M': '--',
        'N': '-.',
        'O': '---',
        'P': '.--.',
        'Q': '--.-',
        'R': '.-.',
        'S': '...',
        'T': '-',
        'U': '..-',
        'V': '...-',
        'W': '.--',
        'X': '-..-',
        'Y': '-.--',
        'Z': '--..',
        '1': '.----',
        '2': '..---',
        '3': '...--',
        '4': '....-',
        '5': '.....',
        '6': '-....',
        '7': '--...',
        '8': '---..',
        '9': '----.',
        '0': '-----',
        '.': '.-.-.-',
        ',': '--..--',
        '?': '..--..',
        '/': '-..-.',
        '@': '.--.-.',
        ' ': '/'
      };
      char = char.toUpperCase();
      return LatinToMorse[char] || '';
    },
  },
};
</script>

<template>
  <div class="bigcontainer">
    <div class="container">
      <h1>Latin to morse converter:</h1>
      <input class="latin-input" v-model="latin" placeholder="write here" maxlength="125" />
      <div class="limit">
        Latin: <br /><span class="latin"> {{ latin }}</span>
        <br />
        Morse: <br /><span class="morse"> {{ convert }}</span>
        <!-- <span>loremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsum</span> -->
        <br />
      </div>
    </div>
  </div>
</template>

<style scoped>
/* ::selection {
  background-color: rgb(255, 63, 63);
} */

.latin {
  color: rgb(132, 132, 255);
  text-transform: uppercase;
}

.morse {
  color: rgb(255, 136, 136);
}

/* .bigcontainer {
  position: relative;
  display: flex;
  overflow-wrap: break-word;
} */

/* .limit {
  overflow-wrap: break-word;
}

.container {
  position: absolute;
  border: 5px solid white;
  padding: 0.125rem 0.5rem;
  overflow-wrap: break-word;
} */

.latin-input {


  border: 0;
  border-bottom: 1.5px solid rgba(235, 235, 235, 0.64);
  outline: 0;

  color: rgba(235, 235, 235, 0.64);
  width: 200px;
  padding: 7px 0;
  background: transparent;
  transition: border-color 0.2s;
  display: flex;
  justify-content: center;
  align-items: center;

}

.latin-input:focus {
  padding-bottom: 6px;
  font-size: 17px;
  border-width: 3px;
  border-image: linear-gradient(to right, rgb(132, 132, 255), rgb(255, 136, 136));
  border-image-slice: 1;

  background: linear-gradient(to right, rgb(132, 132, 255), rgb(255, 136, 136));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>
