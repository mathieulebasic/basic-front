<template>
  <!-- Main navigation container -->
  <nav class="navigation sticky">
    <div class="mobileNavigation">
      <a href="https://freecodecamp.org" class="logo">
        <img
          src="https://s3.amazonaws.com/freecodecamp/freecodecamp_logo.svg"
          alt="freeCodeCamp logo"
        />
      </a>
      <button
        class="block border-0 bg-transparent lg:hidden"
        type="button"
        data-te-target="#navElements"
        aria-controls="navElements"
        aria-expanded="false"
        aria-label="Toggle navigation"
        @click="ouvreMenu"
      >
        <!-- Hamburger icon -->
        <span class="[&>svg]:w-7">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
            fill="currentColor"
            class="h-7 w-7"
          >
            <path
              fill-rule="evenodd"
              d="M3 6.75A.75.75 0 013.75 6h16.5a.75.75 0 010 1.5H3.75A.75.75 0 013 6.75zM3 12a.75.75 0 01.75-.75h16.5a.75.75 0 010 1.5H3.75A.75.75 0 013 12zm0 5.25a.75.75 0 01.75-.75h16.5a.75.75 0 010 1.5H3.75a.75.75 0 01-.75-.75z"
              clip-rule="evenodd"
            />
          </svg>
        </span>
      </button>
    </div>
    <div class="navElements" :class="{ menuvisible: menuVisible }">
      <input
        v-if="barreVisible"
        type="search"
        class="barrederecherche"
        placeholder="Cherchez un territoire"
        aria-label="Search"
        aria-describedby="button-addon3"
      />
      <ul id="menu">
        <li class="menuelements">
          <span><a href="#">Accueil</a></span>
        </li>
        <li class="menuelements">
          <span><a href="#test">Lien Lienx</a></span>
        </li>
      </ul>
      <slot name="boutonContact"></slot>
    </div>
  </nav>
  <bandeauEntete>
    <template v-slot:message>
      <h3>Site en construction</h3>
    </template>
  </bandeauEntete>
</template>

<script>
import bandeauEntete from "@/composants/bandeauEntete.vue";
export default {
  name: "EnTete",
  components: {
    bandeauEntete,
  },
  props: {
    barreVisible: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      menuVisible: false,
    };
  },
  methods: {
    ouvreMenu() {
      this.menuVisible = !this.menuVisible;
    },
  },
};
</script>

<style scoped>
.navigation {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: var(--color-primary);
  justify-content: space-between;
  padding: 0 20px;
}

.mobileNavigation {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navElements {
  display: none;
  align-items: stretch;
}

.menuvisible {
  display: flex;
  flex-direction: column;
}

@media screen and (min-width: 1024px) {
  .navigation {
    flex-direction: row;
    justify-content: space-between;
    height: 100px;
    align-items: stretch;
  }
  .navElements {
    display: flex;
  }

  #menu {
    display: flex;
    padding: 0 var(--dsem2);
  }

  #menu li {
    background-color: var(--couleur-primaire-sombre);
    padding: 15px 20px;
    align-items: center;
  }

  .menuelements {
    display: inline-flex;
  }

  .barrederecherche {
    opacity: 0.8;
    border-radius: 0px;
    padding: 8px 16px;
    margin-left: 10px;
    align-self: center;
  }
  .barrederecherche:focus {
    outline: none !important;
    opacity: 1;
    border: 0px;
  }

  .sticky {
    position: sticky;
    top: 0;
  }
}
</style>
