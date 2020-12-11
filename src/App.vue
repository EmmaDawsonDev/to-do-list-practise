<template>
  <div class="wrapper">
    <input
      type="text"
      placeholder="✏️ To do...	"
      v-model="currentItem"
      @keyup.enter="addItem"
    />
    <ul>
      <list-item
        v-for="(item, index) of toDoItems"
        :key="index"
        :id="index"
        :listItem="item"
        @removeItem="removeFromList(item)"
      ></list-item>
    </ul>
  </div>
</template>

<script>
import ListItem from "./components/ListItem.vue";

export default {
  components: { ListItem },
  data() {
    return {
      currentItem: "",
      toDoItems: [],
    };
  },
  methods: {
    addItem() {
      this.toDoItems.push(this.currentItem);
      this.currentItem = "";
      console.log(this.toDoItems);
    },
    removeFromList(name) {
      let index = this.toDoItems.indexOf(name);
      this.toDoItems.splice(index, 1);
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+JP&display=swap");

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.wrapper {
  max-width: 300px;
  margin: 20px auto;
}

body {
  font-family: "Noto Sans JP", sans-serif;
}

input {
  width: 100%;
  background-color: rgb(167, 211, 255);
  padding: 1.2rem 1rem;
  border: none;
  font-size: 1rem;
  font-weight: bold;
  color: rgb(46, 46, 46);
}

input::placeholder {
  font-size: 1rem;
  font-weight: bold;
  color: rgb(46, 46, 46);
}
</style>
