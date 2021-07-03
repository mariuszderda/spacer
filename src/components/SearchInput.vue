<template>
  <div class="searchWrapper">
    <input
      id="search"
      name="search"
      class="search"
      type="text"
      v-model="searchValue"
      @input="handleInput"
    />
  </div>
</template>

<script>
export default {
  name: 'SearchInput',
};
</script>

<style lang="scss" scoped>
.searchWrapper {
  display: flex;
  flex-direction: column;
  width: 300px;

  input {
    background: none;
    margin-top: 50px;
    height: 30px;
    border: 0;
    border-bottom: 2px solid black;
  }
}
</style>
