<template>
  <div id="app">

    <myMain />

  </div>
</template>

<script>
import myMain from './components/myMain.vue';

export default {
  name: 'App',
  components: {
    myMain
  }
}
</script>

<style lang="scss">

@import "./assets/style/global";
@import "./assets/style/utils";

</style>
