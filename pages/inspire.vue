

<template>
  <v-layout>
    <v-flex class="text-center">
      <div class="text-center">
      <img
        src="/vv.png"
        alt="Vuetify.js"
        class="mb-4 "
        height="120"
      >
      </div>
<v-container fill-eheight>
  <v-layout align-center justify-center>
    <v-flex xs12 sm8 md4 >
      <v-form >
            <v-card class="elevation-20">
              <v-toolbar class="white--text"   color="teal darken-3">
                <v-toolbar-title justify-center>
                  Formule de Connexion


                </v-toolbar-title>

              </v-toolbar>

                <v-card-text >
                  <v-text-field
                  name="Email"
                  label="Email"
                  type="text"

                  >
                 </v-text-field>
                  <v-text-field
                  name="Mot de passe"
                  label="Mot de passe "
                  type="password">
                  </v-text-field>

                  <v-divider light> </v-divider>
                  <v-card-actions >

                    <v-btn round color="teal darken-3" >Se connecter

                    </v-btn>

                  </v-card-actions>


                </v-card-text>
            </v-card>
      </v-form>
    </v-flex>
  </v-layout>
</v-container>


    </v-flex>
  </v-layout>
</template>
7

<script>
import List from './List'
export default {

}
</script>
