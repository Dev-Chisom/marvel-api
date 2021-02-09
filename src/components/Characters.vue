<template>
  <div>
    <h3>Hello Characters</h3>
    <ul>
      <li v-for="character in characters" :key="character.id">
        <!-- <router-link :to="{ name: 'character', params: { id: character.id } }"></router-link>
          {{ character.name }}</router-link
        > -->
        <router-link :to="{ name: 'Character', params: { id: character.id } }">
          {{ character.name }}</router-link
        >
      </li>
    </ul>
  </div>
</template>

<script>
import { public_key, secret_key } from '../marvel';
import axios from 'axios';
export default {
  name: 'Characters',
  data() {
    return {
      characters: [],
    };
  },
  mounted() {
    this.getCharacters();
  },
  methods: {
    getCharacters: function() {
      axios
        .get(
          `http://gateway.marvel.com/v1/public/characters?&apikey=${public_key}`
        )
        .then((result) => {
          //   console.log(result);
          result.data.data.results.forEach((item) => {
            console.log(item);

            this.characters.push(item);
          });
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style></style>
