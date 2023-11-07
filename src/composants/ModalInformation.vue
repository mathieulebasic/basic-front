<template>
  <div id="modal">
    <div id="logoModal" class="texte-moyen">
      <svg
        width="16px"
        height="16px"
        stroke="blue"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 512 512"
      >
        <!--! Font Awesome Pro 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
        <path
          d="M256 512A256 256 0 1 0 256 0a256 256 0 1 0 0 512zM216 336h24V272H216c-13.3 0-24-10.7-24-24s10.7-24 24-24h48c13.3 0 24 10.7 24 24v88h8c13.3 0 24 10.7 24 24s-10.7 24-24 24H216c-13.3 0-24-10.7-24-24s10.7-24 24-24zm40-208a32 32 0 1 1 0 64 32 32 0 1 1 0-64z"
        />
      </svg>
    </div>
    <div id="contenuModal" class="texte-moyen">
      <slot name="message">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim
        veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
        commodo consequat. Duis aute irure dolor in reprehenderit in voluptate
        velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint
        occaecat cupidatat non proident, sunt in culpa qui officia deserunt
        mollit anim id est laborum.
      </slot>
    </div>
  </div>
</template>

<style>
#modal {
  width: 1000px;
  height: fit-content;
  background-color: white;
  border-radius: 0px;
  border: 1px solid var(--couleur-accent-clair);
  border-left: 8px solid var(--couleur-accent);
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: flex-start;
  padding: var(--dsem) var(--dsem2);
  margin: 80px;
  gap: var(--dsem);
}

#logoModal {
  display: flex;
  align-self: flex-start;
  align-items: center;
  height: 24px;
}

#contenuModal {
  text-align: left;
}
</style>
