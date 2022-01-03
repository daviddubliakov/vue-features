<template>
  <div class="container pt-5" v-cloak>
    <div class="card center">
      <div v-html="myHtml"></div>
      <!-- <h2 v-text="title"></h2>
      <h2 v-once>{{ title }}</h2>
      <h2 v-pre>{{ title }}</h2>
      <button class="btn" @click="title = 'I was changed'">Chage title</button> -->
      <ul class="list" v-if="items.length">
        <!-- <li class="list-item" v-for="(item, index) in 7" :key="index">
          {{ item }}
        </li> -->
        <!-- <li class="list-item" v-for="(value, index) in person" :key="index">
          <strong>{{ index }}</strong> {{ value }}
        </li> -->
        <li
          class="list-item"
          v-for="(value, index) in items"
          :key="index"
          @click="items.splice(index, 1)"
        >
          <strong>{{ value }}</strong>
        </li>
      </ul>
      <h3 v-show="items.length === 0">No elements</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    myHtml: "<h1>Vue 3 App</h1>",
    title: "I'm Grut",
    person: {
      firstName: "David",
      lastName: "Dubliakov",
      age: 19,
    },
    items: [1, 2, 3, 4, 5, 6],
  }),
};
</script>
