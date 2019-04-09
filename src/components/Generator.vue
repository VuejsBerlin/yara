<template>
  <section class="result">
    <small>You got</small>
    <h2>{{ verb }}</h2>
    <h1>{{ name }}</h1>
    <button @click="generate">
      <ClientOnly>
        <sweetalert-icon icon="error" />
      </ClientOnly>
    </button>
    <button @click="accept">
      <ClientOnly>
        <sweetalert-icon icon="success" />
      </ClientOnly>
    </button>
  </section>
</template>

<script>
import CatNames from 'cat-names'
import DogNames from 'dog-names'
import Superb from 'superb'

export default {
  data () {
    return {
      verb: '...',
      name: '?!¿¡'
    }
  },
  mounted () {
    this.generate()
  },
  methods: {
    generate () {
      this.verb = Superb.random()
      this.name = Math.random() < .5 ? CatNames.random() : DogNames.allRandom()
    },
    accept () {
      this.$emit('input', { verb: this.verb, name: this.name })
    }
  }
}
</script>

<style scoped>
.result {
  display: block;
  width: 500px;
  max-width: 90vw;
  margin: auto;
  font-size: 2em;
}
.result > h1,
.result > h2 {
  margin: 0;
  background: black;
  color: white;
}
.result > h1 {
  margin-bottom: 1em;
  padding-bottom: 1em;
}
.result > h2 {
  margin-top: 1em;
  padding-top: 1em;
}
.result button {
  width: 150px;
  height: 150px;
  margin: 0 .5em;
  padding: 0;
  background: white;
  overflow: hidden;
  border: 5px solid black;
}
</style>
