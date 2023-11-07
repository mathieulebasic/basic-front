<template>
  <EnTete2 barreVisible="true">
    <template #boutonContact>
      <div style="display: flex; align-items: center">
        <BoutonStandard couleur="couleur-secondaire" taille="texte-moyen"
          >Test</BoutonStandard
        >
      </div>
    </template>
  </EnTete2>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App for UI components" />
    <BrandButton
      v-for="colors in colors"
      :color="colors"
      :key="colors"
      class="mx-2 mb-2 rounded-none"
    >
      <span class="capitalize">{{ colors }}</span>
    </BrandButton>
    <button class="btn btn-primary bg-green-200">Primary</button>
  </div>
  <h2 class="ml-6 mt-3 text-lg font-semibold">Sizes</h2>
  <div class="flex items-end p-4">
    <div v-for="size in sizes" :key="size">
      <BrandButton :size="size" class="mx-2 mb-2">
        <span class="capitalize">{{ size }}</span>
      </BrandButton>
    </div>
  </div>
  <h2 class="ml-6 mt-3 text-lg font-semibold">Icons</h2>
  <div class="flex flex-wrap items-end p-4">
    <BrandButton class="mx-2 mb-2">
      <i class="far fa-edit mr-1" />
      <span>Edit</span>
    </BrandButton>
  </div>
  <BoutonStandard couleur="couleur-primaire" taille="titre-moyen"
    >Test</BoutonStandard
  >
  <Dropdown />
  <ModalInformation />
</template>

<script>
import EnTete2 from "@/composants/EnTete2.vue";
import HelloWorld from "@/composants/HelloWorld.vue";
import BrandButton from "@/composants/BrandButton.vue";
import BoutonStandard from "@/composants/BoutonStandard.vue";
import ModalInformation from "@/composants/ModalInformation.vue";

export default {
  name: "HomeView",
  components: {
    HelloWorld,
    BrandButton,
    EnTete2,
    BoutonStandard,
    ModalInformation,
  },
  data() {
    return {
      colors: ["blue", "yellow", "brand-main"],
      sizes: ["lg", "md", "sm"],
    };
  },
};
</script>
