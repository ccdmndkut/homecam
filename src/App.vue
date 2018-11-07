<template>
  <v-app>
    <v-content>
      <v-container> <cams /> </v-container>
    </v-content>
  </v-app>
</template>

<script>
import cams from "./components/cams";

export default {
  name: "App",
  components: {
    cams
  },
  data() {
    return {
      //
    };
  }
};
</script>
