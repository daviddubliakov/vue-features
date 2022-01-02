<template>
  <div class="container pt-5">
    <div class="card center">
      <h2 v-text="title"></h2>
      <h2 v-once>{{ title }}</h2>
      <h2 v-pre>{{ title }}</h2>
      <button class="btn" @click="title = 'I was changed'">Chage title</button>
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
