<template lang="pug">
  #app
    img(src="./assets/logo.png")
    h1 {{ msg }}
    p(v-show="showValue") {{ value }}
    ul
      li(v-for="i in mensaje") {{ i }}
    input(v-model="year")
    p {{ age }}
    input(v-model="name")
    button(v-on:click="format") Format
    p {{ formattedName }}
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      name: "",
      formattedName: "",
      msg: 'hola Diego',
      value: 'algo',
      showValue: true,
      year: "",
      mensaje: ["besame", "la", "boquita"]
    }
  },
  computed: {
    age () {
      return 2019 - parseInt(this.year)
    }
  },

  methods: {
    format () {
      this.formattedName = this.name.split(" ").join("-")
    }
  }

}
</script>

<style lang="scss">
  @import './scss/main.scss'
</style>
