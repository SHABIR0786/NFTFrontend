<template>
  <div class='home'>
    <header><p>Portfolio</p>
    <div><p>ETH</p><div class="circle-block"><i class="fa-solid fa-left-long"></i><i class="fa-solid fa-right-long"></i></div></div></header>
    <SparkLine />
    <Collection />
  </div>
</template>
<script>
import SparkLine from "./SparkLine.vue";
import Collection from "./Collection.vue";
export default {
  components: { SparkLine, Collection },
  data() {
    return {};
  },
};
</script>
