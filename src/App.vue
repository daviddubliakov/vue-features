<template>
  <div class="container pt-5" v-cloak>
    <div class="card center">
      <div v-html="myHtml"></div>
      <!-- <h2 v-text="title"></h2>
      <h2 v-once>{{ title }}</h2>
      <h2 v-pre>{{ title }}</h2>
      <button class="btn" @click="title = 'I was changed'">Chage title</button> -->
      <ul class="list">
        <li class="list-item" v-for="(item, index) in 7" :key="index">
          {{ item }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    myHtml: "<h1>Vue 3 App</h1>",
    title: "I'm Grut",
  }),
};
</script>
