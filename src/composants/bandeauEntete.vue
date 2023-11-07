<template>
  <div id="entete">
    <slot name="message"></slot>
  </div>
</template>

<script>
export default {
  setup() {},
};
</script>

<style scoped>
#entete {
  background-color: var(--couleur-primaire-sombre);
  height: 50px;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}
</style>
