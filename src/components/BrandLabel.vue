<template>
  <div>
    <span :class="myTextClass">Uber</span> <span class="brand-green" :class="textClass">Eats</span>
  </div>
</template>
<script>
export default {
  props: {
    textClass: {
      type: String,
    },
    textVariant: {
      type: String,
      default: "black",
    },
  },
  computed: {
    myTextClass() {
      return `brand-${this.textVariant} font-weight-bold ${this.textClass}`;
    },
  },
};
</script>

<style scoped>
.brand-black {
  font-weight: bold;
  color: white;
}
.brand-black {
  font-weight: bold;
  color: black;
}
.brand-green {
  font-weight: bold;
  color: rgb(18, 119, 48);
}
</style>
