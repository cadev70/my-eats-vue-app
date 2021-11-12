<template>
  <b-navbar class="header">
    <b-icon-list
      font-scale="2"
      class="mr-2 pointer"
      v-b-toggle.sidebar-backdrop
    ></b-icon-list>
    <BrandLabel textClass="h2"></BrandLabel>
    <b-button pill size="md" class="ml-auto mr-md-2" variant="light">
      登入
    </b-button>
  </b-navbar>
</template>
<script>
import BrandLabel from "@/components/BrandLabel";

export default {
  components: {
    BrandLabel,
  },
};
</script>
<style scoped>
.header {
  height: 3rem;
  background: rgba(255, 255, 255, 0.3);
  padding: 0.5rem 0.5rem;
}
.pointer {
  cursor: pointer;
}
.pointer:focus {
  outline: none;
}
</style>
