<template>

<!--    <ul>-->
<!--      <li v-for="item in results" :key="item.data[0].nasa_id">-->
<!--        <p>{{ item.data[0].description }}</p>-->
<!--      </li>-->
<!--    </ul>-->
</template>

<script>
import axios from 'axios';
import debounce from 'lodash.debounce';
import Claim from '@/components/Claim.vue';
import SearchInput from '@/components/SearchInput.vue';

const API = 'https://images-api.nasa.gov/search';

export default {
  name: 'Home',
  components: {
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
      axios.get(`${API}?q=${this.searchValue}&media_type=image`).then((response) => {
        this.results = response.data.collection.items;
      }).catch((error) => {
        console.log(error);
      });
    }, 500),
  },
};
</script>

<style lang="scss" scoped>
  .wrapper {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: 0;
    padding: 30px;
    background-image: url("../assets/moon.jpg");
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
  }

</style>
