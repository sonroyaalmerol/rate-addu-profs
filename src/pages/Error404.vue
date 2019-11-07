<template>
  <div class="fixed-center text-center">
    <p>
      <img
        class="svg"
        src="~assets/sad.svg"
        style="width:30vw;max-width:150px;"
      >
    </p>
    <p class="text-faded text-white">Sorry, nothing here...<strong>(404)</strong></p>
    <q-btn
      color="primary"
      style="width:200px;"
      to="/"
      label="Go back"
    />
  </div>
</template>

<script>
export default {
  name: 'Error404',
};
</script>

<style scoped>
  .svg {
    filter: invert(.5) sepia(0) saturate(5) brightness(100);
  }
</style>
