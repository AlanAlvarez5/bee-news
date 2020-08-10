<template>
  <v-app>
    <v-main>
      <Navbar></Navbar>
      <v-container>

        <v-row>
          <v-card
          class="mx-auto my-3"
          max-width="350"
          v-for="noticia in news"
          :key="noticia.url"
          >
            <v-img
              height="200px"
              :src="noticia.urlToImage"
            >

            </v-img>

            <v-card-title>
              {{noticia.title}}
            </v-card-title>

            <v-card-subtitle>
              {{noticia.author}}
            </v-card-subtitle>

            <v-card-text>
              {{noticia.description}}
            </v-card-text>

            <v-card-subtitle>
              {{noticia.publishedAt.slice(0,10)}}
            </v-card-subtitle>

            <v-card-action>
              <v-btn
                color="orange"
                text
                target="_blank"
                :href="noticia.url"
              >
                Ver Noticia
              </v-btn>
            </v-card-action>
            
          </v-card>
        </v-row>
      </v-container>
      


    </v-main>
  </v-app>
</template>

<script>

import Navbar from './components/Navbar'

export default {
  name: 'App',

  components: {
    Navbar
  },

  data: () => ({
    news: {}
  }),

  methods: {

    async getNews(){
      let apiURL = 'http://newsapi.org/v2/top-headlines?country=mx&category=technology&apiKey=19aa6dd2908a492cbb301ed1f2936a02'

      let noticias = await this.axios.get(apiURL)

      this.news = noticias.data.articles
      console.log(this.news)

    }

  },

  created(){
    this.getNews()
  }




};
</script>
