<script>
export default {
  data() {
    return {
      newCharacter: { actor: '', name: '' }
    }
  },
  emits: [ 'add-character' ],
    methods: {
        sendNewCharacter: function (){
            this.$emit('add-character', this.newCharacter);
            this.newCharacter = { actor: '', name: '' };
            }
        }
}
</script>

<template>
  <h2>Add new character</h2>
  <form @submit.prevent="sendNewCharacter">
    <label for="new-character-actor">actor name</label>
    <input type="text" id="new-character-actor" required v-model="this.newCharacter.actor" />
    <br />
    <label for="new-character-name">character name</label>
    <input type="text" id="new-character-name" required v-model="this.newCharacter.name" />
    <br />
    <button type="submit">save!</button>
  </form>
</template>
