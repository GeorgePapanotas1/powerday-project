<template>
  <div class="home">
    <Countdown />
    <MainContent />
  </div>
</template>

<script>
// @ is an alias to /src
import Countdown from "../components/Countdown";
import MainContent from "../components/MainContent.vue";

export default {
  name: "Home",
  components: {
    Countdown,
    MainContent,
  },
};
</script>

<style scoped lang="scss">
.home {
  background-color: rgb(39, 39, 39);
}
</style>
