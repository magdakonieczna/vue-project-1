<template>
  <div class="searchWrapper">
    <div class="search">
      <input id="search" name="search" :value="value" @input="handleChange" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'SearchInput',
  props: {
    value: {
      type: String,
      required: true,
    },
  },
  methods: {
    handleChange(e) {
      this.$emit('input', e.target.value);
    },
  },
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
        font-family: 'Montserrat', sans-serif;
        font-size: 16px;
        text-align: center;
        height: 40px;
        border: 0;
        border-bottom: 1px solid black;
        transition: box-shadow .5s;
        &:focus {
          outline: none;
          box-shadow: 0 10px 20px -8px black;
        }
      }
    }
  }
</style>
