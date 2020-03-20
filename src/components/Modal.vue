<template>
  <div class="outerWrapper">
    <div class="innerWrapper">
      <div class="photo">
        <img src="" alt="">
      </div>
      <div class="description">
        <h2 class="title"></h2>
        <p class="description"></p>
      </div>
    </div>
    <div class="close" @click="$emit('closeModal')"></div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
};
</script>

<style lang="scss" scoped>
  .outerWrapper {
    max-width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    background: #F6F6F6;
    /*position: relative;*/
  }
  .close {
    position: absolute;
    width: 30px;
    height: 30px;
    padding: 30px;
    right: 0;
    top: 0;
    cursor: pointer;
    &::before, &::after {
      position: absolute;
      top: 20px;
      right: 20px;
      content: '';
      width: 100px;
      height: 2px;
      background: black;
      display: block;
    }
    &::before {
      transform: rotate(45deg);
    }
    &::after {
      transform: rotate(-45deg);
    }
  }
  .innerWrapper {
    display: flex;
    height: 100%;
    padding: 50px;
    justify-content: center;
    align-items: center;
    .photo {
      width: 100%;
      height: auto;
      background: black;
      img {
        width: 100%;
      }
    }
    .description {
      color: #333;
    }
  }
</style>
