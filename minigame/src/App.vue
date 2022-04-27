<template>
  <main-screen
    v-if="statusMatch === 'default'"
    @onStart="onHandleBeforeStart($event)"
  />
  <interact-screen v-if="statusMatch === 'match'" />
</template>

<script>
import MainScreen from "./components/MainScreenComp.vue";
import InteractScreen from "./components/InteractScreenComp.vue";
// import ResultScreen from "./components/ResultScreenComp.vue";
// import CopyRight from "./components/CopyRightScreenComp.vue;

export default {
  name: "App",
  data() {
    return {
      statusMatch: "default",
    };
  },
  components: {
    MainScreen,
    InteractScreen,
    // ResultScreen,
    // CopyRight,
  },
  methods: {
    onHandleBeforeStart(config) {
      console.log("running Handle", config);
      this.statusMatch = "match";
    },
  },
};
</script>
