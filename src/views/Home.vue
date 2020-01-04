<template>
  <v-app>
    <div class="home mt-12">
      <br>
      <div class="text-center mt-12 mb-5 display-3">Jorge Jasso</div>
      <v-carousel cycle height="350px" width="100px" :show-arrows="showArrow" hide-delimiters>
        <v-carousel-item v-for="activity in activities" :key="activity">
          <v-sheet color="blue-grey lighten-1" height="80%" >
            <v-row class="fill-height" align="center" justify="center">
              <div class="display-2">{{ activity }}</div>
            </v-row>
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
    </div>
  </v-app>
</template>

<script>
  export default {
    name: 'home',
    components: {

    },
    data: () => ({
      activities: ['Consultant', 'Analyst', 'Programmer', 'Tester'],
      showArrow: false
    }),
  }
</script>
