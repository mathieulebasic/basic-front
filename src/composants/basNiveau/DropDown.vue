<template>
  <div
    @mouseover="SousElementsVisibles = true"
    @mouseleave="SousElementsVisibles = false"
  >
    <span>Titre liste</span>
    <ul v-if="SousElementsVisibles" class="listeSousElements">
      <li v-for="element in listeSousElements" :key="element">
        {{ element }}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      listeSousElements: [
        "Item 1",
        "Item 2",
        "Very very very very long Item 3",
      ],
      SousElementsVisibles: false,
    };
  },
  methods: {
    ouvreMenu() {
      this.SousElementsVisibles = !this.SousElementsVisibles;
    },
  },
};
</script>
<style scoped>
.listeSousElements {
  display: block;
  position: absolute;
  flex-direction: column;
  align-items: start;
  background-color: blueviolet;
  justify-content: space-between;
  padding: 24px 24px;
}
</style>
