<template>
  <div class="selected">
    <div v-if="!multiple && items.length > 0" class="selected__item">
      {{ items[0] }}
    </div>
    <div v-else class="selected__multiple">
      <div class="multiple__item" v-for="item in items" :key="item.id">
        {{ item.name }}
      </div>
      <div v-if="multiple" class="count">
        Selected {{ items.length }}/{{ length }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SelectedItem",
  props: {
    multiple: {
      type: Boolean,
      default: false,
    },
    items: {
      type: Array,
      default: () => [],
    },
    length: {
      type: Number,
      default: null,
    },
  },
};
</script>

<style scoped lang="scss">
.selected {
  position: relative;
  display: flex;
  margin-bottom: 20px;
  border: 1px solid black;
  padding: 5px;
  max-width: 370px;
  min-height: 200px;
  height: auto;

  .selected__multiple {
    position: relative;
    display: flex;
    flex-wrap: wrap;
    padding-bottom: 20px;

    .multiple__item {
      position: relative;
      display: flex;
      border: 1px solid gray;
      padding: 10px;
      margin: 5px;
    }

    .count {
      position: absolute;
      bottom: 0;
      width: 90px;
    }
  }

  .selected__item {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 10px;
    margin: 5px;
    font-size: 40px;
    text-align: center;
  }
}
</style>
