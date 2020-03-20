<template>
<div class="moonImg"></div>
</template>

<script>
export default {
  name: 'MoonImage',
};
</script>

<style lang="scss" scoped>
.moonImg {
  width: 100%;
  height: 100vh;
  position: fixed;
  top: 0;
  z-index: -1;
  background-image: url("../assets/moon.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
</style>
