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
    copy() {
      this.$refs.clone.focus();
      document.execCommand('copy');
    },
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
    <h1>Latin to morse converter:</h1>
    <input class="latin-input" v-model="latin" placeholder="write here" maxlength="100" />
    Latin: <span class="latin"> {{ latin }}</span>
    <br />
    Morse: <br /><textarea class="morse" v-on:focus="$event.target.select()" ref="clone" readonly v-model="convert" />
    <br />
    <button class="copy" @click="copy">Copy</button>
  </div>


</template>

<style scoped>
.container {
  width: 400px;
}

.morse {
  color: rgb(132, 132, 255);
  text-transform: uppercase;
  background-color: transparent;
  outline: 0;
  border: 0;

  border: 1.5px solid rgba(235, 235, 235, 0.64);
  resize: none;
  height: 120px;
  width: 400px;
}

.latin {
  color: rgb(132, 132, 255);
}

.morse {
  color: rgb(255, 136, 136);
}

.latin-input {
  border: 0;
  border: 1.5px solid rgba(235, 235, 235, 0.64);
  outline: 0;

  color: rgba(235, 235, 235, 0.64);
  width: 400px;
  padding: 7px 5px;
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

.copy {
  background-color: transparent;
  color: rgba(235, 235, 235, 0.64);
  outline: 0;
  border: 2px solid rgba(235, 235, 235, 0.64);
  padding: 2px;
}

.copy:hover {
  background-color: transparent;
  color: rgb(255, 136, 136);
  outline: 0;
  border: 2px solid rgb(255, 136, 136);
  padding: 2px;
  cursor: pointer;
}
</style>
