<template>
  <div class="container pt-5">
    <div class="card center">
      <h1 v-text="title"></h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    title: "I'm Grut",
  }),
};
</script>
