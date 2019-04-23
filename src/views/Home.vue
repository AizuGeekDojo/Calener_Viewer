<template>
  <div class="home">
    <Calender />
  </div>
</template>

<script>
// @ is an alias to /src
import Calender from "@/components/calender.vue";

export default {
  name: "home",
  components: {
    Calender
  }
};
</script>

<style scoped>
.home {
  margin: 0;
}
</style>
