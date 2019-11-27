<template>
 <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      class="teal darken-3"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

        <v-container
    fill-height
    fluid
    grid-list-xl>
    <v-layout
      justify-center
      wrap
    >
         <v-container fluid >
       <v-layout align-center justify-center >
         <v-flex xs12 sm8 md4 class="text-center">
           <v-card class="elevation-20" >
             <v-toolbar dark color="teal darken-3">
             <v-spacer>
               <v-toolbar-title >
                 Ajouter Etudiant
               </v-toolbar-title>
              </v-spacer>
             </v-toolbar>
             </v-card>
             </v-flex>
             </v-layout>
    </v-container>
    <v-spacer></v-spacer>
      <v-flex
        xs12
        md8
      >
        <material-card
          color="green"
          title="Edit Profile"
          text="Complete your profile"
        >
          <v-form>
            <v-container py-0>
              <v-layout wrap>

                 <v-flex
                  xs12
                  md6
                >
                  <v-text-field
                    label="Nom"
                    class="purple-input"/>
                </v-flex>
                 <v-flex
                  xs12
                  md4
                >

                </v-flex>
                <v-flex
                  xs12
                  md6
                >
                  <v-text-field
                    label="Prenom"
                    class="purple-input"/>
                </v-flex>
                <v-flex
                  xs12
                  md4
                >

                </v-flex>
                <v-flex
                  xs12
                  md4
                >
                  <v-text-field
                    label="Adresse Email"
                    class="purple-input"/>
                </v-flex>
                 <v-flex
                  xs12
                  md4
                >

                </v-flex>
                        <v-col class="d-flex" cols="15" sm="15">
        <v-select
          :items="itm"
          label="Groupe"
        ></v-select>
        </v-col>
                 <v-flex
                  xs12
                  md14
                >

                </v-flex>

                <v-flex
                  xs12
                  md12
                >

                </v-flex>


                <v-flex
                  xs12
                  text-xs-right
                >

                  <v-btn dark
                    class="mx-0 font-weight-light"
                    color="teal darken-3"
                  >
                    Ajouter au liste des Etudiants
                  </v-btn>
                </v-flex>
              </v-layout>
            </v-container>
          </v-form>
        </material-card>

      </v-flex>
      <v-flex
        xs12
        md4
      >
        <material-card class="v-card-profile">
          <v-avatar
            slot="offset"
            class="mx-auto d-block"
            size="130"
            align-end
          >
            <img
            src="/igg.png"
        alt="Vuetify.js"
        class="mb-4 "
        height="120"
            >
          </v-avatar>
          <v-card-text class="text-xs-center">
            <!--h6 class="category text-gray font-weight-thin mb-3">Pers farada Kamel</h6-->
            <h4 class="card-title font-weight-light">Pers farada Kamel</h4>
            <p class="card-description font-weight-light">....................................................................</p>
            <v-btn dark
              color="teal darken-3"
              round
              class="font-weight-light"
            >Voir le profile</v-btn>
          </v-card-text>
        </material-card>
      </v-flex>
    </v-layout>
  </v-container>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />


      <v-toolbar-title v-text="title" />
      <v-spacer />

    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>

  </v-app>









</template>

<script>
export default {

      data () {

    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {

          title: 'Esi-App',
         icon:"mdi-school",

        },
        {
          title: '',
        },
        {
          icon: 'mdi-home-variant',
          title: 'Accueil',
          to: '/'
        },

        {
          icon: 'mdi-account-circle',
          title: 'Ajouter Etudiant',
          to: '/Ajouter'
        },

        {
          icon: 'mdi-format-list-bulleted',
          title: 'Groupes',
          to: '/List'
        }
        ,
        {
          icon: 'mdi-pen',
          title: 'Planning Examens',
          to: '/Examens'
        },
        {
          icon: 'mdi-marker-check',
          title: 'Consultation Notes',
          to: '/Note'
        }

      ],
      itm: ['1', '2', '3', '4', '5', '6', '7', '8'],

      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Esi-App' ,

    }

  }

}
</script>
