<script>
    export default {
        props: {
            cast: {
                type: Object,
                required: true
            }
        }
    }
</script>
<template>
  <h2>Characters</h2>
  <ul>
    <li v-for="character in this.cast">
      <h3>{{ character.actor }}</h3>
      <p>{{ character.name }}</p>
    </li>
  </ul>
</template>
