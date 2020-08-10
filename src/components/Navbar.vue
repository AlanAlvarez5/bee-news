<template>
     <v-app-bar
          dark
          color="primary"
     >
          <v-img
               alt="Bee Logo"
               class="shrink mr-2"
               contain
               src="../assets/bee-logo.png"
               width="40"
          >

          </v-img>
          <h1>BEE NEWS</h1>

          <v-spacer></v-spacer>

          <v-btn
               href="https://beedevelopers.dev"
               target="_blank"
               text
          >
               <v-icon class="mr-2">fas fa-link</v-icon>
               <span> Web de BeeDevelopers</span>
          </v-btn>
     </v-app-bar>
</template>

<script>
export default {
     name: 'Navbar'
}
</script>