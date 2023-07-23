<script>
import CastList from './components/CastList.vue'
import NewCharacterForm from './components/NewCharacterForm.vue'

export default {
  components: {
    CastList,
    NewCharacterForm
  },
  data() {
    return {
      title: 'The Office',
      cast: [
        { actor: 'Jenna Fischer', name: 'Pam Beasley' },
        { actor: 'Steve Carell', name: 'Michael Scott' }
      ],
      newCharacter: { actor: '', name: '' }
    }
  },
  methods: {
    addNewCharacter: function (character) {
      this.cast.push(character)
    }
  }
}
</script>

<template>
  <h1 id="main-title">{{ this.title }}</h1>
  <CastList :cast="cast" />
  <hr />
  <NewCharacterForm @add-character="addNewCharacter"/>
  <h2>Number of characters: {{ this.cast.length }}</h2>
</template>
