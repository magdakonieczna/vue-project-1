<template>
  <div class="searchWrapper">
    <div class="search">
      <input id="search" type="search" v-model="searchValue" @input="handleInput" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'SearchInput',
};
</script>

<style lang="scss" scoped>
  .searchWrapper {
    margin-top: 50px;
    .search {
      width: 250px;
      display: flex;
      flex-direction: column;
      input {
        background: none;
        height: 30px;
        border: 0;
        border-bottom: 1px solid black;
      }
    }
  }
</style>
