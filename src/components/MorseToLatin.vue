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
        <input class="latin-input" v-model="morse" placeholder="write here" maxlength="125" />

        Morse: <br /><span class="morse"> {{ morse }}</span>

        <br />
        Latin: <br /><span class="latin"> {{ convert }}</span>
        <!-- <span>loremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsumloremipsum</span> -->
    </div>
</template>

<style>
.latin {
    color: rgb(132, 132, 255);
    text-transform: uppercase;
}

.morse {
    color: rgb(255, 136, 136);
}

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

    /* background: linear-gradient(to right, rgb(132, 132, 255), rgb(255, 136, 136));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent; */
}
</style>