/* eslint-disable */
<template>
  <div class="wraper">
    <div class="search">
      <label for="search">Search</label>
      <input type="text" name="search" v-model="searchValue" @input="handleInput" />
    </div>
    <ul>
      <li v-for="result in results" :key="result.data[0].nasa_id">
        <p>{{ result.links[0].href }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';
import debounce from 'lodash.debounce';

const URL = 'https://images-api.nasa.gov/';

export default {
  name: 'Home',
  data() {
    return {
      searchValue: '',
      results: [],
    };
  },
  methods: {
    handleInput: debounce(function () {
      axios.get(`${URL}search?q=${this.searchValue}&media_type=image`)
        .then((respo) => {
          this.results = respo.data.collection.items;
          console.log(respo.data.collection.items);
        })
        .catch((error) => {
          console.log(error);
        });
    }, 500),
  },
};
</script>

<style lang="scss" scoped>
.wraper {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0;
  padding: 0;
  width: 100%;
}

.search {
  display: flex;
  flex-direction: column;
  width: 300px;

  label {
    font-family: Montserrat, sans-serif;
    font-weight: bold;
  }
  input {
    height: 30px;
    border: 0;
    border-bottom: 1px solid black;
  }
}
</style>
