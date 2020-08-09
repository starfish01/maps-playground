<template>
  <div class="home">
    <div class="container">
      <Map />
    </div>
  </div>
</template>

<script>
import Map from "@/components/Map/Map.vue";

export default {
  name: "home",
  components: {
    Map,
  },
};
</script>
