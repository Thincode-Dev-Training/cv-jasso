<template>
  <v-app>
    <v-container id="container" class="grey lighten-2">
      <v-row>
        <v-col cols="3">
          <br>
          <v-card class="mt-12">
            <v-img src="../src/assets/image.png" aspect-ratio="1" class="teal lighten-4"></v-img>
            <v-list class="teal darken-4">
              <v-list-item-group>
                <v-list-item v-for="(item, i) in items" :key="i">
                  <v-list-item-icon>
                    <v-icon v-text="item.icon" class="white--text"></v-icon>
                  </v-list-item-icon>
                  <router-link id="routerlink" :to="item.route">
                    <v-list-item-content :to="item.route">
                      <v-list-item-title v-text="item.text" class="white--text"></v-list-item-title>
                    </v-list-item-content>
                  </router-link>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-card>
        </v-col>
        <v-col cols="9">
          <router-view id="routerview" class="teal lighten-4"/>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
  export default {
    name: 'App',
    data: () => ({
      items: [
        { route: '/', text: 'Home', icon: 'mdi-home' },
        { route: '/about', text: 'About me', icon: 'mdi-account-circle' },
        { route: '/resume', text: 'Resume', icon: 'mdi-account-card-details' }
      ]
    })
  };
</script>

<style scoped>
  #container{
    box-shadow: 5px 0px 10px black, -5px 0px 10px black;
  }
  #routerlink{
    display: inline-block;
    width: 300px;
    text-decoration: none;
  }
  #routerview{
    height: 88%;
    margin-top:10px;
  }
</style>