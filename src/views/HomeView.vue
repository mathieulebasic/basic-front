<template>
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
    <IconsSVG name="arrrow-left" class="w-6 h-6 mr-1" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import BrandButton from "@/components/BrandButton.vue";
import IconsSVG from "@/components/IconsSVG.vue";

export default {
  name: "HomeView",
  components: {
    HelloWorld,
    BrandButton,
    IconsSVG,
  },
  data() {
    return {
      colors: ["blue", "yellow", "brand-main"],
      sizes: ["lg", "md", "sm"],
    };
  },
};
</script>
