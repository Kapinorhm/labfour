<template>
  <div class="body">
    <header>
      <button v-on:click="navigateTo('elements')">View elements</button>
      {{basket.length}} in basket
      <button v-on:click="navigateTo('basket')">View basket</button>
    </header>

    <div v-if="page === 'basket'">
      <basket v-on:removeItemFrombasket="removeItemFrombasket" :basket="basket" />
    </div>

    <div v-if="page === 'elements'">
      <elements v-on:addItemTobasket="addItemTobasket" />
    </div>
  </div>
</template>

<script>
import elements from "./components/elements.vue";
import basket from "./components/basket.vue";
export default {
  name: "App",
  data: () => {
    return {
      page: "elements",
      basket: []
    };
  },
  methods: {
    addItemTobasket(item) {this.basket.push(item);},
    removeItemFrombasket(item) {this.basket.splice(this.basket.indexOf(item), 1);},
    navigateTo(page) {this.page = page;}},
  components: { elements, basket }
};
</script>

<style>
.elements button {padding: 11px;background-color: #FCDE9C; color: black;cursor: pointer;}
.elements {display: grid;grid-template-columns: 1fr 1fr;}
</style>

<style scoped>
header button {padding: 10px;border: none;cursor: pointer;color: #C4D6B0;
background-color: #381D2A;font-size: 25px;margin: 0px 30px 0px 30px; }
header {height: 100px;box-shadow: 2px 2px 15px #FFA552;background-color: #BA5624;
  text-align: center;font-size: 42px;padding-top: 25px;}
.body{background-color: #BCF4DE;}
</style>