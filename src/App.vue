<template lang="pug">
  #app
    section.section
      nav.nav.has-shadow
        .container
          input.input.is-large(
            type="text",
            placeholder="Buscar canciones",
            v-model="searchQuery"
          )
          a.button.is-info.is-large(v-on:click="search") Buscar
          a.button.is-danger.is-large &times;
          p
            small {{ searchMessage }}

      .container.results
        .columns
          .column(v-for="t in tracks") {{t.name}} - {{t.artista}}
</template>

<script>
const tracks = [
  {name: 'Diego', artista: 'Fernando'},
  {name: 'Rodriguez', artista: 'Orejuela'}
]

export default {
  name: 'app',
  data () {
    return {
      searchQuery: '',
      tracks: []
    }
  },
  computed: {
    searchMessage(){
      return `te quiero mucho: ${this.tracks.length}`
    }
  },

  methods: {
    search () {
        this.tracks = tracks
    }
  }

}
</script>

<style lang="scss">
  @import './scss/main.scss';

.results {
  margin-top: 50px
}

</style>
