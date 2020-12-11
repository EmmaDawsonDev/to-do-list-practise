<template>
  <div>
    <p>{{ listItem }}</p>
    <span @click="removeItem(listItem)">X</span>
  </div>
</template>

<script>
export default {
  props: {
    listItem: String,
  },
  methods: {
    removeItem(item) {
      this.$emit("removeItem", item);
    },
  },
};
</script>

<style scoped>
div {
  background-color: rgb(240, 240, 240);
  width: 100%;
  padding: 1rem;
  display: flex;
}

div:nth-of-type(2n) {
  background-color: rgb(212, 212, 212);
}

p {
  min-width: 95%;
}
</style>
