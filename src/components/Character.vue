<template>
  <div>
    <h3>Hello this is single</h3>
    <p>{{ this.$route.params.id }}</p>
    <ul>
      <li v-for="char in character" :key="char.id">
        {{ char.name }} {{ char.description }}
      </li>
    </ul>
    <img :src="url" :alt="[url]" />
  </div>
</template>

<script>
import { public_key } from '../marvel';
import axios from 'axios';
export default {
  name: 'Character',
  data() {
    return {
      character: [],
      url: '',
      size: 'standard_large.jpg',
    };
  },
  mounted() {
    this.getCharacter();
  },
  methods: {
    getCharacter: function() {
      let characterId = this.$route.params.id;
      axios
        .get(
          `http://gateway.marvel.com/v1/public/characters/${characterId}?&apikey=${public_key}`
        )
        .then((result) => {
          //   console.log(result);

          result.data.data.results.forEach((item) => {
            // console.log(item);

            this.character.push(item);

            this.url = `${item.thumbnail.path}${this.size}`;

            console.log(this.url);
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
