<script>
import AppHeader from "@/components/AppHeader.vue";
export default {
  components: {
    AppHeader,
  },
};
</script>
<template>
  <AppHeader />
  <div class="container mt-3">
    <router-view />
  </div>
</template>
<style>
#app {
  width: 100%;
  display: flex;
  flex-direction: column;
  position: fixed;
  left: 50%;
  top: 0;
  transform: translateX(-50%);
}

.page {
  max-width: 400px;
  margin: auto;
}
</style>