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
           <v-layout align-center justify-center >
         <v-flex xs12 sm8 md4 class="text-center">
           <v-card class="elevation-20" >
             <v-toolbar dark color="teal darken-3">
             <v-spacer>
               <v-toolbar-title >
                 Liste Etudiant
               </v-toolbar-title>
              </v-spacer>
             </v-toolbar>
             </v-card>
             </v-flex>
             </v-layout>
            </v-layout>
            </v-container>

         <v-simple-table>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">Nom / Prenom </th>
          <th class="text-left">Email</th>
          <th class="text-left">Groupe</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in desserts" :key="item.name">
          <td>{{ item.name }}</td>
          <td>{{ item.email }}</td>
          <td>{{ item.groupe }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
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
          title: 'List Groupe',
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
      desserts: [
          {
            name: 'Etudiant1',
            email:'....@esi.dz',
            groupe: 5,
          },
          {
            name: 'Etudiant2',
            email:'....@esi.dz',
            groupe:5,
          },
          {
            name: 'Etudiant3',
            email:'....@esi.dz',
            groupe: 5,
          },
          {
            name: 'Etudiant4',
            email:'....@esi.dz',
            groupe: 5,
          },
          {
            name: 'Etudiant5',
            email:'....@esi.dz',
            groupe:5,
          },
          {
            name: 'Etudiant6',
            email:'....@esi.dz',
            groupe: 5,
          },
          {
            name: 'Etudiant7',
            email:'....@esi.dz',
            groupe: 5,
          },
          {
            name: 'Etudiant8',
            email:'....@esi.dz',
            groupe:5,
          },
          {
            name: 'Etudiant9',
            email:'....@esi.dz',
            groupe: 5,
          },
          {
            name: 'Etudiant10',
            email:'....@esi.dz',
            groupe: 5,
          },
        ],

      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Esi-App' ,

    }
  },
  }
</script>
