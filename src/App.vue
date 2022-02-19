<template>
  <v-app>    
    <v-main>
      <v-row class="text-center">
        <v-col cols="12">
          <v-img
            :src="require('./assets/logo.svg')"
            class="my-3"
            contain
            height="200"
          />
        </v-col>
      </v-row>
      <v-row class="text-center">
        <v-col cols="12">
        <Titulo texto="Mi banco dinamico 2.0"/>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12">
        <Cuenta/>
        </v-col>
      </v-row>      
    </v-main>
  </v-app>
</template>

<script>
//import HelloWorld from './components/HelloWorld';
import Titulo from './components/Titulo.vue';
import Cuenta from './components/Cuenta.vue';

export default {
  name: 'App',
  components: {
    Titulo,
    Cuenta
  },
  data: () => ({
    //
  }),
};
</script>
