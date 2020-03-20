<template>
  <div class="searchWrapper">
    <div class="search">
      <input
        id="search"
        name="search"
        :class="{ dark: dark }"
        :value="value"
        @input="handleChange" />
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
    dark: {
      type: Boolean,
      default: false,
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
      .dark {
        color: #1e3d4a;
        border-bottom-color: #1e3d4a;
        &:focus {
          outline: none;
          box-shadow: 0 10px 20px -8px rgba(#1e3d4a, .2);
        }
      }
    }
  }
</style>
