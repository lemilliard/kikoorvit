<template>
  <v-card>
    <v-toolbar>
      <v-btn fab dark @click.stop="speedUp">
        <v-icon>keyboard_arrow_up</v-icon>
      </v-btn>
      <v-btn fab dark>
        {{ 13 - speed }}
      </v-btn>
      <v-btn fab dark @click.stop="speedDown">
        <v-icon>keyboard_arrow_down</v-icon>
      </v-btn>
    </v-toolbar>
    <v-card-title>
      <img :src="`/static/Kikoorvit ${speedChar}.gif`"/>
    </v-card-title>
  </v-card>
</template>

<script>
  export default {
    name: 'Shoe',
    data() {
      return {
        speed: 2,
      };
    },
    computed: {
      speedChar() {
        if (this.speed < 10) {
          return `0${this.speed}`;
        }
        return this.speed;
      },
    },
    methods: {
      speedDown() {
        if (this.speed < 12) {
          this.speed += 1;
        }
      },
      speedUp() {
        if (this.speed > 2) {
          this.speed -= 1;
        }
      },
    },
  };
</script>

<style scoped>
  img {
    background: white;
  }
</style>
