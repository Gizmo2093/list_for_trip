<template>
  <v-app id="inspire">
    <v-app-bar app>
      <v-toolbar-title>Brand</v-toolbar-title>

      <v-spacer />

      <v-btn icon x-large @click="editProfile">
        <v-avatar>
          <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John">
        </v-avatar>
      </v-btn>

    </v-app-bar>

    <main>
      <Home />
    </main>

  </v-app>
</template>

<script>
import Home from './views/Home.vue'
export default {
  name: 'App',
  data: () => ({
    user: {
      initials: 'VE',
      fullName: 'Vladimir',
      email: '123@gmail.com',
    }
  }),
  components:{
    Home
  },
  methods:{
    editProfile(){
      console.log("Перенаправление на страницу редактирования профиля");
    }
  }
};
</script>
