<template>
  <div class="container pt-5" v-cloak>
    <div class="card center">
      <div v-html="myHtml"></div>
      <!-- <h2 v-text="title"></h2>
      <h2 v-once>{{ title }}</h2>
      <h2 v-pre>{{ title }}</h2>
      <button class="btn" @click="title = 'I was changed'">Chage title</button> -->
      <div class="form-control">
        <input type="text" @keyup.shift.enter="addItem" ref="myInput" />
      </div>
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
          :key="value"
          @click.right.prevent="remove(index), log(value)"
        >
          <strong>{{ value }}</strong
          >&nbsp;
          <input type="text" @click.stop />
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
  methods: {
    addItem() {
      this.items.unshift(this.$refs.myInput.value);
      this.$refs.myInput.value = "";
    },
    remove(index) {
      this.items.splice(index, 1);
    },
    log(item) {
      console.log('Log item:', item);
    }
  },
  computed: {
    evenItems() {
      return this.items.filter((item) => item % 2 === 0);
    },
  },
};
</script>
