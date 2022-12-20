<script>
export default {
    data() {
        return {
            morse: '',
        }
    },
    computed: {
        convert() {
            return this.morse.split(' ').map(char => this.abc(char)).join('');
        },
    },
    methods: {
        copy() {
            this.$refs.clone.focus();
            document.execCommand('copy');
        },
        abc(char) {
            const MorseToLatin = {
                '.-': 'A',
                '-...': 'B',
                '-.-.': 'C',
                '-..': 'D',
                '.': 'E',
                '..-.': 'F',
                '--.': 'G',
                '....': 'H',
                '..': 'I',
                '.---': 'J',
                '-.-': 'K',
                '.-..': 'L',
                '--': 'M',
                '-.': 'N',
                '---': 'O',
                '.--.': 'P',
                '--.-': 'Q',
                '.-.': 'R',
                '...': 'S',
                '-': 'T',
                '..-': 'U',
                '...-': 'V',
                '.--': 'W',
                '-..-': 'X',
                '-.--': 'Y',
                '--..': 'Z',
                '.----': '1',
                '..---': '2',
                '...--': '3',
                '....-': '4',
                '.....': '5',
                '-....': '6',
                '--...': '7',
                '---..': '8',
                '----.': '9',
                '-----': '0',
                '.-.-.-': '.',
                '--..--': ',',
                '..--..': '?',
                '/': ' ',
                '.--.-.': '.--.-.',
                ' ': ' '
            }
            return MorseToLatin[char] || '';
        },
    },
};
</script>

<template>
    <div class="container">
        <h1>Morse to latin converter:</h1>
        <input class="latin-input" v-model="morse" placeholder="write here" maxlength="100" />
        Morse: <span class="morse"> {{ morse }}</span>
        <br />
        Latin: <br /><textarea class="latin" v-on:focus="$event.target.select()" ref="clone" readonly
            v-model="convert" />
        <br />
        <button class="copy" @click="copy">Copy</button>
    </div>
</template>

<style scoped>
.container {
    width: 500px;
}

.latin {
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
    color: rgb(132, 132, 255);
    outline: 0;
    border: 2px solid rgb(132, 132, 255);
    padding: 2px;
    cursor: pointer;
}
</style>