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
  <div class="container">
    <div>
      <h1>Latin to morse converter:</h1>
    </div>
    <div>
      <input class="latin-input" v-model="latin" placeholder="write here" maxlength="30" />
    </div>
    <div class="limit">
      Latin <span class="latin"> {{ latin }}</span>
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

/* .container {
  border: 5px solid white;
  padding: 0.125rem 0.5rem;

  width: 50%;
  height: 75%;
  overflow-wrap: break-word;
} */
.latin-input {

  width: fit-content;
  border: 0;
  border-bottom: 1.5px solid var(--color-text);
  outline: 0;

  color: var(--color-text);
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
}
</style>
