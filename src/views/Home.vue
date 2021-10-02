<template>
  <v-main class="">
    <v-toolbar dark color="teal">
      <v-autocomplete cache-items class="mx-4" flat hide-no-data hide-details label="Куда отправимся сегодня?" solo-inverted/>
      </v-toolbar>

    <v-container>
      <v-row>
        <v-col
          v-for="n in 24"
          :key="n"
          cols="4"
        >
          <v-card height="200">
            {{ countries }}
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script>
const axios = require('axios').default;
  export default {
    name: 'Home',
    data: () =>({
      msg: 'Home page',
      countries: null,
    }),
    components: {

    },
    mounted(){
      axios
        .get('http://testslim/countries/all',{
          headers: { 
            'Access-Control-Allow-Origin' : '*',
          },
        })
        .then(response => (this.countries = response))
    }
  }
</script>

<style scoped>
#Home{
  margin-top: 150px;
}
</style>
