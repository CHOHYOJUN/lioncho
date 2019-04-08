<template>
  <v-container
  grid-list-lg
  >
    <v-data-iterator
      items="4"
      content-tag="v-layout"
      hide-actions
      row
      wrap
    >
      <template v-slot:item="props">
        <v-flex xs12 sm6 md4 lg3>
          <v-card>
            <v-card-title
            class="subheading font-weight-bold green lighten-4" >JAVA</v-card-title>
            <v-divider></v-divider>
            <v-list dense>
              <v-list-tile
              v-for="jList in javaLists" :key="jList"
              >
                <v-list-tile-content
                class="font-weight-bold"
                >{{jList}}</v-list-tile-content>
              </v-list-tile>
            </v-list>
          </v-card>
        </v-flex>

         <v-flex xs12 sm6 md4 lg3>
          <v-card>
            <v-card-title class="subheading font-weight-bold light-blue lighten-4">JavaScript</v-card-title>
            <v-divider></v-divider>
            <v-list dense>
              <v-list-tile
              v-for="jsList in jsLists" :key="jsList"
              >
                <v-list-tile-content
                class="font-weight-bold"
                >{{jsList}}</v-list-tile-content>
              </v-list-tile>
            </v-list>
          </v-card>
        </v-flex>

          <v-flex xs12 sm6 md4 lg3>
          <v-card>
            <v-card-title class="subheading font-weight-bold amber lighten-4">DB</v-card-title>
            <v-divider></v-divider>
            <v-list dense>
              <v-list-tile
              v-for="dbList in dbLists" :key="dbList"
              >
                <v-list-tile-content
                class="font-weight-bold"
                >{{dbList}}</v-list-tile-content>
              </v-list-tile>
            </v-list>
          </v-card>
        </v-flex>

          <v-flex xs12 sm6 md4 lg3>
          <v-card>
            <v-card-title class="subheading font-weight-bold lime lighten-4">Cloud Service</v-card-title>
            <v-divider></v-divider>
            <v-list dense>
              <v-list-tile
              v-for="clList in clLists" :key="clList"
              >
                <v-list-tile-content  class="font-weight-bold ">{{clList}}</v-list-tile-content>
              </v-list-tile>
            </v-list>
          </v-card>
        </v-flex>
      </template>
    </v-data-iterator>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      javaLists: [
          "- JSP : 중",
          "- Servlet : 중",
          "- Strutrs2 : 중",
          "- Spring : 중",
          "- SpringBoot : 중",
          "- MyBitys3 : 중",

      ],
      jsLists: [
          "- HTML, CSS",
          "- jQuery, Ajax",
          "- Bootstrap, Bulma",
          "* Vue.js ",
          "- Vuex, Vuetyfy.js, Nuxt.js",
          "- Node.js"
      ],
      dbLists: [
          "- MySql",
          "- Oracle",
          "- MongoDB"


      ],
      clLists: [
        "- AWS",
        "- Firebase",
        "- TOAST(NHN)",
      ],

    })
  }
</script>