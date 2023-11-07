<template>
  <a :class="definirStyle">
    <slot></slot>
  </a>
</template>
<script>
export default {
  props: {
    href: {
      required: false,
      type: String,
      default: null,
    },
    type: {
      type: String,
      default: "relief", //relief, encadre, plat
    },
    couleur: {
      type: String,
      default: "couleur-secondaire", // couleur-primaire, couleur-secondaire, couleur-accent
    },
    taille: {
      type: String,
      default: "titre-petit", // texte-petit, texte-moyen, titre-petit, titre-moyen, titre-grand
    },
    outline: Boolean,
    round: Boolean,
    square: Boolean,
  },
  computed: {
    definirStyle() {
      const classeCouleur =
        this.couleur === "couleur-primaire"
          ? "theme-primaire"
          : this.couleur === "couleur-secondaire"
          ? "theme-secondaire"
          : "theme-accent";
      const classeType =
        this.type === "encadre"
          ? "theme-encadre"
          : this.type === "relief"
          ? "theme-relief"
          : "theme-plat";
      return classeCouleur + " " + classeType + " " + this.taille;
    },
  },
};
</script>

<style scoped>
a {
  cursor: pointer;
  align-items: center;
  width: fit-content;
  justify-content: center;
  text-decoration: none;
  padding: 8px 16px;
  background-color: var(--couleur-fond-base);
  color: var(--couleur-texte-base);
}

a:hover {
  background-color: var(--couleur-fond-active);
  color: var(--couleur-texte-active);
}

.theme-primaire {
  --couleur-choisie: var(--couleur-primaire);
  --couleur-choisie-sombre: var(--couleur-primaire-sombre);
}

.theme-secondaire {
  --couleur-choisie: var(--couleur-secondaire);
  --couleur-choisie-sombre: var(--couleur-secondaire-sombre);
}

.theme-encadre {
  --couleur-fond-base: var(--couleur-blanc);
  --couleur-texte-base: var(--couleur-choisie);
  --couleur-fond-active: var(--couleur-choisie);
  --couleur-texte-active: var(--couleur-blanc);
}

.theme-relief {
  --couleur-fond-base: var(--couleur-choisie);
  --couleur-texte-base: var(--couleur-blanc);
  --couleur-fond-active: var(--couleur-choisie-sombre);
  --couleur-texte-active: var(--couleur-blanc);
}
</style>
