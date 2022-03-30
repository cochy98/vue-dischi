<template>
  <!-- Single card -->
  <div class="col">
    <div class="card h-100">
      <img :src="discInfo.poster" class="card-img-top" :alt="discInfo.title" />
      <div class="card-body text-center">
        <h3 class="card-title">{{ discInfo.title }}</h3>
        <p class="card-text m-0">{{ discInfo.author }}</p>
        <p class="card-text">{{ discInfo.year }}</p>
      </div>
    </div>
  </div>
  <!-- /Single card -->
</template>

<script>
export default {
  name: "SingleDisc",
  props: {
    discInfo: Object,
  },
};
</script>

<style>
</style>
