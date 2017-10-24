<template>
  <v-layout>
    <v-flex xs12>
      <shoe></shoe>
    </v-flex>
  </v-layout>
</template>

<script>
  import Shoe from '@/components/Shoe';

  export default {
    name: 'HelloWorld',
    components: { Shoe },
    data() {
      return {
        msg: 'Welcome to Your Vue.js App',
      };
    },
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>
