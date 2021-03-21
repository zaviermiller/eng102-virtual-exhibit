<template>
  <v-app>
    <v-main>
      <VirtualExhibit/>
    </v-main>
  </v-app>
</template>

<script>
import VirtualExhibit from './components/VExhibit';

export default {
  name: 'App',

  components: {
    VirtualExhibit,
  },

  data: () => ({
    //
  }),
};
</script>
