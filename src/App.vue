<template>
  <v-app>
    <div>
      <v-row>
        <v-col cols="3" class="mt-12">
          <v-card class="mx-auto" max-width="300">
            <v-img
              src="../src/assets/images.jpg"
              aspect-ratio="1"
              class="grey lighten-2"
              max-width="500"
              max-height="500">
            </v-img>
            <v-list>
              <v-list-item-group>
                <v-list-item v-for="(item, i) in items" :key="i">
                  <v-list-item-icon>
                    <v-icon v-text="item.icon"></v-icon>
                  </v-list-item-icon>
                  <router-link :to="item.route" id="routerlink" class="black--text">
                    <v-list-item-content :to="item.route">
                      <v-list-item-title v-text="item.text"></v-list-item-title>
                    </v-list-item-content>
                  </router-link>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-card>
        </v-col>
        <v-col cols="9">
          <v-content>
            <router-view/>
          </v-content>
        </v-col>
      </v-row>
    </div>
  </v-app>
</template>

<script>
  export default {
    name: 'App',
    components: {

    },
    data: () => ({
      items: [
        {
          route: '/',
          text: 'Home',
          icon: 'mdi-home',
        },
        {
          route: '/about',
          text: 'About',
          icon: 'mdi-account-circle',
        },
        {
          route: '/resume',
          text: 'Resume',
          icon: 'mdi-account-card-details',
        },
      ],
    }),
  };
</script>

<style scoped>
  #routerlink{
    display: inline-block;
    width: 300px;
    text-decoration: none;
  }
</style>