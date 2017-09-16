<template>
  <v-app id="example-1" toolbar footer>
    <v-navigation-drawer
      persistent
      v-model="drawer"
      light
      absolute
    >
      <v-list dense>
        <v-list-tile @click="">
          <v-list-tile-action>
            <v-icon>home</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Home</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar class="red" dark fixed>
      <v-toolbar-side-icon @click.stop="drawer = !drawer" class="hidden-sm-and-up"></v-toolbar-side-icon>
      <v-toolbar-title>Toolbar</v-toolbar-title>
        <v-spacer></v-spacer>
          <v-toolbar-items class="hidden-xs-only">
            <v-btn flat>
              <v-icon left>home</v-icon>
              Home
            </v-btn flat>
          </v-toolbar-items>
    </v-toolbar>
    <main>
      <v-container fluid>
        <!--v-router-->
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
        drawer: false
      }
    }
  }
</script>
