<template>
  <div class="items">
    <div
      class="items__item"
      v-for="item in items"
      :key="item.id"
      @click="click(item.id)"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<script>
export default {
  name: "ItemsContainer",
  props: {
    items: {
      type: Object,
      default: () => {},
    },
  },
  methods: {
    click(id) {
      this.$emit("add", id);
    },
  },
};
</script>

<style scoped lang="scss">
.items {
  position: relative;
  display: flex;
  padding: 5px;
  border: 1px solid black;
  flex-wrap: wrap;

  .items__item {
    position: relative;
    display: flex;
    width: auto;
    height: fit-content;
    align-items: center;
    justify-content: center;
    padding: 20px;
    margin: 10px;
    border: 1px solid gray;
    cursor: pointer;
  }
}
</style>
