<template>
  <v-app id="example-1" toolbar footer>
    <v-navigation-drawer
      persistent
      v-model="drawer"
      light
      absolute
      temporary
    >
      <v-list dense>
        <v-list-tile @click="" v-for="item in menuItems" :key="item.title" router :to='item.link'>
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>{{ item.title }}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar class="red" dark fixed>
      <v-toolbar-side-icon @click.stop="drawer = !drawer" class="hidden-sm-and-up"></v-toolbar-side-icon>
      <v-toolbar-title><router-link to='/' tag='span' style='cursor: pointer'>Toolbar</router-link></v-toolbar-title>
        <v-spacer></v-spacer>
          <v-toolbar-items class="hidden-xs-only">
            <v-btn flat v-for="item in menuItems" :key="item.title" router :to='item.link'>
              <v-icon left>{{ item.icon }}</v-icon>
              {{ item.title }}
            </v-btn flat>
          </v-toolbar-items>
    </v-toolbar>
    <main>
      <v-container fluid>
        <!--v-router-->
        <router-view></router-view>
      </v-container>
    </main>
    <v-footer class="red">
      <span class="white--text">© 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        drawer: false,
        menuItems: [
          { icon: 'home', title: 'Home', link: '/' },
          { icon: 'info_outline', title: 'About', link: '/about' },
          { icon: 'face', title: 'Sign Up', link: '/signup' },
          { icon: 'lock_open', title: 'Sign In', link: 'signin' }
        ]
      }
    }
  }
</script>
