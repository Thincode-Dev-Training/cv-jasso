<template>
  <v-app>
      <span class="shadow display-3 text-center white--text mt-12 mb-7">Jorge Jasso</span>
      <v-carousel cycle interval="3500" height="380px">
        <v-carousel-item v-for="(activity, i) in activities" :key="i">
          <v-sheet color="teal darken-4" height="84%" >
            <v-row align="center" justify="center" class="fill-height">
              <span class="shadow display-1">{{ activity }}</span>
            </v-row>
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
  </v-app>
</template>

<script>
  export default {
    name: 'Home',
    data: () => ({ activities: ['Consultant', 'Analyst', 'Programmer', 'Tester'] })
  };
</script>

<style scoped>
  .shadow{
    text-shadow: 4px 4px 5px black;
  }
</style>