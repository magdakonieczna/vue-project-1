<template>
  <div class="claimWrapper">
    <h1 class="claim">SPACER</h1>
    <p class="subclaim">
      Begin your journey through our amazing galaxy, and discover places you never even heard of.
    </p>
    <p class="subclaim">Type anything space-related to start.</p>
  </div>
</template>
<script>
export default {
  name: 'Claim',
};
</script>
<style lang="scss" scoped>
  .claimWrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    .claim {
      font-size: 50px;
      margin: 0;
    }
    .subclaim {
      width: 500px;
      margin: 20px 0 0 0;
      font-size: 13px;
      text-align: center;
      font-weight: 300;
      letter-spacing: 1px;
      @media (max-width: 768px) {
        width: 100%;
      }
    }
  }
</style>
