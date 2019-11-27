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
          icon: 'mdi-account-box',
          title: 'Connexion',
          to: '/inspire'
        },
        {
          icon: 'mdi-checkbox-multiple-marked-outline',
          title: 'Inscription',
          to: '/signup'
        }

      ],

      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Esi-App' ,

    }
  }
}
</script>
