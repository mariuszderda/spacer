<template>
  <div class="wrapper">
    <Claim/>
    <SearchInput/>
  </div>
</template>

<script>
import axios from 'axios';
import debounce from 'lodash.debounce';
import Claim from '@/components/Claim.vue';
import SearchInput from '@/components/SearchInput.vue';

const API = 'https://images-api.nasa.gov/search?';
// @ is an alias to /src

export default {
  name: 'Search',
  components: {
    SearchInput,
    Claim,
  },
  data() {
    return {
      searchValue: '',
      results: [],
    };
  },
  methods: {
    // eslint-disable-next-line
    handleInput: debounce(function () {
      axios.get(`${API}q=${this.searchValue}&media_type=image`)
        .then((response) => {
          this.results = response.data.collection.items;
        })
        .catch((error) => {
          console.log(error);
        });
    }, 500),
  },
};
</script>

<style lang="scss" scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100vh;
  padding: 30px;
  margin: 0;
  background-image: url('../assets/heroimage.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 80% 0;
}
</style>
