<template>
  <button
    class="font-medium flex items-center cursor-pointer border shadow hover:shadow-lg focus:outline-none focus:shadow-outline"
    :href="href"
    :type="type"
    :class="style"
  >
    <slot></slot>
  </button>
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
      default: "button", //button, submit
    },
    id: {
      type: String,
      required: false,
    },
    name: {
      type: String,
      required: false,
    },
    color: {
      type: String,
      default: "teal",
    },
    size: {
      type: String,
      default: "md", //sm, md, lg
    },
    outline: Boolean,
    round: Boolean,
    square: Boolean,
  },
  computed: {
    colorClasses() {
      const color = this.color;
      const baseClasses = `bg-${color}-600 text-${color}-100 border-${color}-600 hover:bg-${color}-700 hover:border-${color}-700 hover:text-white`;
      const outlineClasses = `border-${color}-600 bg-white text-${color}-600 hover:bg-${color}-600 hover:border-${color}-600 hover:text-white`;
      return this.outline ? outlineClasses : baseClasses;
    },
    sizeClasses() {
      const sizeMappings = {
        sm: `h-8 text-sm px-4`,
        md: `h-10 px-6`,
        lg: `text-lg h-12 px-12`,
      };

      return sizeMappings[this.size] || sizeMappings.md;
    },

    style() {
      const styles = {
        default: "btn btn-primary bg-cyan-100 border-cyan-500 text-cyan-700",
        red: "btn btn-primary bg-red-100 border-red-500 text-red-700",
        orange:
          "btn btn-primary bg-orange-100 border-orange-500 text-orange-700",
        green: "btn btn-primary bg-green-100 border-green-500 text-green-700",
        blue: "btn btn-primary bg-blue-100 border-blue-500 text-blue-700",
      };
      const couleurClasse = styles[this.color] ?? styles.default;

      const borderRadiusClasses = this.round
        ? "rounded-full"
        : this.square
        ? "rounded-none"
        : "rounded";
      return `${this.sizeClasses} ${couleurClasse} ${borderRadiusClasses}`;
    },
    buttonType() {
      if (this.href) {
        return "a";
      } else {
        return "button";
      }
    },
  },
};
</script>
