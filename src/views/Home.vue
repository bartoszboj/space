/* eslint-disable */
<template>
  <div class="wrapper">
    <HeroImage />
    <Heading />
    <SearchInput />
  </div>
</template>

<script>
import axios from 'axios';
import debounce from 'lodash.debounce';
import Heading from '@/components/Heading.vue';
import SearchInput from '@/components/SearchInput.vue';
import HeroImage from '@/components/HeroImage.vue';

const URL = 'https://images-api.nasa.gov/';

export default {
  name: 'Home',
  data() {
    return {
      searchValue: '',
      results: [],
    };
  },
  components: {
    Heading,
    SearchInput,
    HeroImage,
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
    }, 1000),
  },
};
</script>

<style lang="scss">
.wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: 0;
  padding: 30px;
  width: 100%;
  height: 100vh;
}
</style>
