<template>
  <v-app toolbar>
    <v-toolbar app class="primary" dark>
      <img src="/static/img/Niglo%2001.png" style="max-width: 90px; cursor: pointer;" @click.stop="niglo = true"/>
      <v-toolbar-title>Kikoorvit</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-title>Le Bon Djo</v-toolbar-title>
      <img src="/static/img/Fist%2001.png" style="max-width: 60px; cursor: pointer;" @click.stop="fist = true"/>
    </v-toolbar>
    <main>
      <v-content>
        <v-dialog v-model="niglo" max-width="600px">
          <v-card>
            <v-layout justify-center align-center>
              <img src="/static/img/Niglo%2002.gif"/>
            </v-layout>
            <v-card-title primary-title>
              <h2>La chaussure Kikoorvit</h2>
            </v-card-title>
          </v-card>
        </v-dialog>
        <v-dialog v-model="fist" max-width="320px">
          <v-card>
            <v-layout justify-center align-center>
              <img src="/static/img/Fist%2001.png"/>
            </v-layout>
            <v-card-title primary-title>
              <h2>J'en veuuux</h2>
            </v-card-title>
          </v-card>
        </v-dialog>
        <v-container>
          <v-layout justify-center>
            <img :src="`/static/img/Kikoorvit ${speedChar}.gif`" :style="`max-width: ${windowSize.x}px`"/>
          </v-layout>
        </v-container>
      </v-content>
    </main>
    <v-footer app class="lime accent-3" absolute>
      <v-spacer></v-spacer>
      <v-btn icon @click.stop="speedDown">
        <v-icon>keyboard_arrow_down</v-icon>
      </v-btn>
      <v-btn icon @click.stop="speedReset">
        {{ 13 - speed }}
      </v-btn>
      <v-btn icon @click.stop="speedUp">
        <v-icon>keyboard_arrow_up</v-icon>
      </v-btn>
      <v-spacer></v-spacer>
    </v-footer>
  </v-app>
</template>

<script>
  require('vuetify/dist/vuetify.min.css');

  export default {
    data() {
      return {
        niglo: false,
        fist: false,
        speed: 12,
        windowSize: {
          x: 0,
          y: 0,
        },
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
    mounted() {
      this.onResize();
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
      speedReset() {
        this.speed = 12;
      },
      onResize() {
        this.windowSize = { x: window.innerWidth, y: window.innerHeight };
      },
    },
  };
</script>

<style scoped>
</style>
