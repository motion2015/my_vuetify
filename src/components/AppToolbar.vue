<template>
<div>
  <v-toolbar color="orange darken-4" dark>
    <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
    <router-link to="/">
      <v-toolbar-title class="white--text">Bitfumes</v-toolbar-title>
    </router-link>
    <v-spacer></v-spacer>
    <v-badge right>
      <span slot="badge" class="white--text">6</span>
      <v-icon
        color="black lighten-1"
      >fa fa-bell
      </v-icon>
    </v-badge>
    <div class="hidden-sm-and-down">
      <v-btn flat>About</v-btn>
      <router-link to="/contact">
        <v-btn flat>Contact</v-btn>
      </router-link>
      <router-link to="/login">
        <v-btn flat>Login</v-btn>
      </router-link>      
    </div>
    
  </v-toolbar>
  <div class="hidden-md-and-up">
          <v-navigation-drawer
            v-model="drawer"
            absolute
            temporary
            height="400px"
          >
            <v-list class="pa-1">
              <v-list-tile avatar>
                <v-list-tile-avatar>
                  <img src="https://randomuser.me/api/portraits/men/85.jpg">
                </v-list-tile-avatar>

                <v-list-tile-content>
                  <v-list-tile-title>John Leider</v-list-tile-title>
                </v-list-tile-content>
              </v-list-tile>
            </v-list>

            <v-list class="pt-0" dense>
              <v-divider></v-divider>

              <v-list-tile
                v-for="item in items"
                :key="item.title"
                @click=""
              >
                <v-list-tile-action>
                  <v-icon>{{ item.icon }}</v-icon>
                </v-list-tile-action>

                <v-list-tile-content>
                  <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                </v-list-tile-content>
              </v-list-tile>
            </v-list>
          </v-navigation-drawer>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      drawer: null,
      items: [
        { title: 'Home', icon: 'dashboard' },
        { title: 'About', icon: 'question_answer' }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

</style>
