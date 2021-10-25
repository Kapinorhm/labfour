<template>
  <div>
    <h1>Your basket</h1>
    <div class="elements">
      <div v-for="(item, index) in basket" :key="index">
        <h3>{{item.name}}</h3>
        <img :src="item.image" />
        <div>{{item.cost}}</div>
        <button v-on:click="removeItemFrombasket(item)">Remove from basket</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["basket"],
  methods: {
    removeItemFrombasket(item) {
      this.$emit("removeItemFrombasket", item);
    }
  }
};
</script>