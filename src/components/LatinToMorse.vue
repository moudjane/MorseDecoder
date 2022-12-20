<script>
export default {
  data() {
    return {
      latin: '',
    }
  },
  computed: {
    convert() {
      return this.latin.split('').map(char => this.abc(char)).join('/');
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
        // '/': '-..-.',
        '@': '.--.-.',
      };
      char = char.toUpperCase();
      return LatinToMorse[char] || '';
    },
  },
};
</script>

<template>
  <div>
    <div>
      <h1>Latin to morse converter:</h1>
    </div>
    <div>
      <input v-model="latin" id="latin" placeholder="write here">
    </div>
    <div>
      Latin text: <span class="latin"> {{ latin }}</span>
      <br />
      Morse: <span class="morse"> {{ convert }}</span>
    </div>
  </div>
</template>

<style scoped>
.latin {
  color: rgb(132, 132, 255);
}

.morse {
  color: rgb(255, 136, 136);
}
</style>
