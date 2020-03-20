<template>
  <div class="wrapper">
    <MoonImage />
    <Claim />
    <SearchInput  v-model="searchValue" @input="handleInput" />
  </div>
</template>
<script>
import axios from 'axios';
import debounce from 'lodash.debounce';
import Claim from '@/components/Claim.vue';
import SearchInput from '@/components/SearchInput.vue';
import MoonImage from '@/components/MoonImage.vue';

const API = 'https://images-api.nasa.gov/search';

export default {
  name: 'Home',
  components: {
    MoonImage,
    Claim,
    SearchInput,
  },
  data() {
    return {
      searchValue: '',
      results: [],
    };
  },
  methods: {
    handleInput: debounce(function Moon() {
      console.log(this.searchValue);
      axios.get(`${API}?q=${this.searchValue}&media_type=image`).then((response) => {
        this.results = response.data.collection.items;
      }).catch((error) => {
        console.log(error);
      });
    }, 500),
  },
};
</script>
<style lang="scss">
  @import url('https://fonts.googleapis.com/css?family=Montserrat:300,400,600,800&display=swap&subset=latin-ext');
  * {
    box-sizing: border-box;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
  body {
    font-family: 'Montserrat', sans-serif;
    margin: 0;
    padding: 0;
  }
  .wrapper {
    width: 100%;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: 0;
    padding: 30px;
  }
</style>
