<template>
  <div>
    <h1>elements</h1>
    <div class="elements">
      <div v-for="(item, index) in elements" :key="index">
        <h3>{{item.name}}</h3>
        <div class="cost">{{item.cost}}</div>
        <img :src="item.image" />
        <button v-on:click="addItemTobasket(item)">Add to basket</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      elements: [
        {
          name: "Dofus des Glaces",
          cost: "17,99zł",
          image:
            "https://www.dofuspourlesnoobs.com/uploads/1/3/0/1/13010384/custom_themes/586567114324766674/files/Dofus/dofusdesglaces.png"
        },
        {
          name: "Dofus Vulbis",
          cost: "30,99zł",
          image:
            "https://www.dofuspourlesnoobs.com/uploads/1/3/0/1/13010384/vulbis_orig.png"
        },
        {
          name: "Dofus Abyssal",
          cost: "10,99zł",
          image:
            "https://www.dofuspourlesnoobs.com/uploads/1/3/0/1/13010384/dofusabyssal_orig.png"

        },
         {
          name: "Dofus Forgelave",
          cost: "7,99zł",
          image:
            "https://www.dofuspourlesnoobs.com/uploads/1/3/0/1/13010384/dofus-forgelave_orig.png"

        },
         {
          name: "Dofus Nebuleux",
          cost: "25,99zł",
          image:
            "https://www.dofuspourlesnoobs.com/uploads/1/3/0/1/13010384/nebuleux_orig.png"
        },
         {
          name: "Dofus Tachete",
          cost: "32,99zł",
          image:
            "https://www.dofuspourlesnoobs.com/uploads/1/3/0/1/13010384/dfs1-tachete_orig.png"
        },
         {
          name: "Dofus Ebene",
          cost: "18,99zł",
          image:
            "https://www.dofuspourlesnoobs.com/uploads/1/3/0/1/13010384/dofusebene_1_orig.png"

        },
         {
          name: "Dofus Abyssal",
          cost: "21,99zł",
          image:
            "https://www.dofuspourlesnoobs.com/uploads/1/3/0/1/13010384/dofusivoire_1_orig.png"

        }
      ]
    };
  },
  methods: {
    addItemTobasket(item) {
      this.$emit("addItemTobasket", item);
    }
  }
};
</script>