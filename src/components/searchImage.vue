<template>
  <v-container>
    <v-row class="mt-5">
      <v-text-field label="Search image" class="pr-2"></v-text-field>
      <v-btn color="primary">
       <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-row>
    <div>{{info}}</div>
  </v-container>
</template>

<script>
import axios from 'axios'
  export default {
    name: 'searchImage',

    data: () => ({
      info: null
    }),

    methods: {
      mounted(){
        axios
          .get('https://pokeapi.co/api/v2/evolution-chain')
          .then(response => (this.info = response))
      }
    }
  }
</script>
