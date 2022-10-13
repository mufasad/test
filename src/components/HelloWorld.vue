<template>
  <div class="container">
    <div class="left">
      <selected-item
        :multiple="true"
        :items="selectedLeft"
        :length="left.length"
      />
      <items-container :items="left" @add="addLeft" />
    </div>
    <div class="right">
      <selected-item :items="selectedRight" />
      <items-container :items="right" @add="addRight" />
    </div>
  </div>
</template>

<script>
import ItemsContainer from "@/components/ItemsContainer";
import SelectedItem from "@/components/SelectedItem";
export default {
  name: "HelloWorld",
  components: {
    ItemsContainer,
    SelectedItem,
  },
  data() {
    return {
      left: [
        {
          id: 1,
          name: "Shoes 1",
        },
        {
          id: 2,
          name: "Shoes 2",
        },
        {
          id: 3,
          name: "Shoes 3",
        },
        {
          id: 4,
          name: "Shoes 4",
        },
        {
          id: 5,
          name: "T-shirt 1",
        },
        {
          id: 6,
          name: "T-shirt 2",
        },
        {
          id: 7,
          name: "T-shirt 3",
        },
        {
          id: 8,
          name: "T-shirt 4",
        },
      ],
      right: [
        {
          id: 11,
          name: "Jacket 1",
        },
        {
          id: 12,
          name: "Jacket 2",
        },
        {
          id: 13,
          name: "Jacket 3",
        },
        {
          id: 14,
          name: "Jacket 4",
        },
        {
          id: 15,
          name: "Hoodie 1",
        },
        {
          id: 16,
          name: "Hoodie 2",
        },
        {
          id: 17,
          name: "Hoodie 3",
        },
        {
          id: 18,
          name: "Hoodie 4",
        },
      ],
      selectedLeft: [],
      selectedRight: [],
    };
  },
  methods: {
    addLeft(id) {
      const index = this.left.findIndex((x) => x.id === id);
      if (this.selectedLeft.length < 6) {
        if (!this.selectedLeft.find((x) => x.id === id)) {
          this.selectedLeft.push(this.left[index]);
        }
      }
    },
    addRight(id) {
      const index = this.right.findIndex((x) => x.id === id);
      this.selectedRight = [];
      this.selectedRight.push(this.right[index].name);
    },
  },
};
</script>

<style scoped lang="scss">
.container {
  position: relative;
  display: flex;
  padding: 20px;

  .left {
    margin-right: 20px;
  }
}
</style>
