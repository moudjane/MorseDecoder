<script>
import LatinToMorse from "./components/LatinToMorse.vue"
import MorseToLatin from "./components/MorseToLatin.vue"
export default {
  data() {
    return {
    }
  },
  components: {
    LatinToMorse: LatinToMorse,
    MorseToLatin: MorseToLatin,
  }
}
</script>

<template>
  <LatinToMorse />
  <br />
  <MorseToLatin />
</template>

<style scoped>

</style>
