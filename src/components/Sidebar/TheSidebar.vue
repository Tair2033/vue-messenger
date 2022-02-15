<template>
  <div class="sidebar" id="sidebar">
    <the-brand/>
  </div>
</template>

<script>
import TheBrand from "@/components/TheBrand";
export default {
  components: {TheBrand}
}
</script>

<style scoped>
.sidebar {
  box-shadow: rgba(0, 0, 0, 0.14) 0px 0px 5px 2px;
  display: flex;
  flex-direction: column;
  width: 280px;
  min-width: 280px;
  position: relative;
  z-index: 2;
}


</style>