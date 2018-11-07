<template>
  <v-layout>
    <v-flex xs12 sm6 offset-sm3>
      <v-card>
        <v-img
          ripple
          :class="{ active: isActive }"
          ref="vid"
          :src="currentcam"
          :aspect-ratio="16 / 9"
        ></v-img>
        <v-card-title primary-title>
          <div>
            <h3 class=" headline mb-0">{{ camtitle }}</h3>
          </div>
        </v-card-title>

        <v-card-actions>
          <v-btn @click="campick(true);" flat color="orange">Front</v-btn>
          <v-btn @click="campick(false);" flat color="orange">
            Family Room
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  name: "cams",
  props: {},
  data() {
    return {
      camA: true,
      camtitle: "test",
      front: "http://192.168.0.04:81/mjpg/hik/video.mjpg",
      family: "http://192.168.0.04:81/mjpg/foscam/video.mjpg"
    };
  },
  methods: {
    campick(c) {
      this.camA = c;
    }
  },
  computed: {
    currentcam() {
      if (this.camA) {
        return this.front;
      } else {
        return this.family;
      }
    },
    imgwidth() {
      var r = this.$refs("vid");
      return r.width;
    }
  }
};
</script>
html{ }
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style></style> //
<div v-ripple>// <img :src="vid" /> //</div>
