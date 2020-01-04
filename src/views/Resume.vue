<template>
  <v-app>
    <div class="resume">
      <v-row>
        <v-col cols="4">
          <v-card max-width="350" tile>
            <h1 class="text-center">Skill</h1>
            <v-list-item v-for="(skill, i) in skills" :key="i">
              <v-list-item-content>
                <v-list-item-title>
                  <span class="ml-3">{{skill.text}}</span>
                  <v-progress-linear :value="skill.level" class="mt-1" height="7"></v-progress-linear>
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-card>
        </v-col>
        <v-col cols="8">
          <v-card max-width="570" tile>
            <h1 class="text-center">Education</h1>
            <v-list-item v-for="(item, i) in education" :key="i">
              <v-list-item-content>
                <v-list-item-title>
                  <span class="ml-3"> {{item.text}} </span>
                  <br>
                  <span class="ml-3"> {{item.generation}} </span>
                  <br>
                  <span class="ml-3"> {{item.specialty}} </span>
                  <br>
                  <span class="ml-3"> {{item.degree}} </span>
                  <br>
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-card>
          <br>
          <v-card max-width="570" tile>
            <h1 class="text-center">Soft Skill</h1>
              <v-carousel cycle height="100px" width="100px" :show-arrows="showArrow" hide-delimiters>
                <v-carousel-item v-for="skill in soft_skills" :key="skill">
                  <v-sheet color="blue-grey lighten-1" height="100%" >
                    <v-row class="fill-height" align="center" justify="center">
                      <div class="display-2">{{ skill }}</div>
                    </v-row>
                  </v-sheet>
                </v-carousel-item>
              </v-carousel>
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="4">
          <v-card max-width="350" tile>
            <h1 class="text-center">Languages</h1>
            <v-list-item v-for="(language, i) in languages" :key="i">
              <v-list-item-content>
                <v-list-item-title>
                  <span class="ml-3"> {{language.text}} </span>
                  <v-progress-linear :value="language.level" class="mt-1" height="7"></v-progress-linear>
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-card>
        </v-col>
        <v-col cols="8">
          <v-card max-width="570" tile>
            <h1 class="text-center">Experience</h1>
            <v-list-item v-for="(item, i) in experience" :key="i">
              <v-list-item-content>
                <v-list-item-title>
                  <span class="ml-3"> {{item.period}} </span>
                  <br>
                  <span class="ml-3"> {{item.company}} </span>
                  <br>
                  <span class="ml-3"> {{item.job}} </span>
                  <br>
                  <span class="ml-3"> {{item.task}} </span>
                  <br>
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-card>
        </v-col>
      </v-row>

    </div>
  </v-app>
</template>

<script>
  export default {
    name: 'resume',
    components: {

    },
    data: () => ({
      skills: [
        {
          text: 'Ruby, Ruby on Rails',
          level: 60
        },
        {
          text: 'Java',
          level: 60
        },
        {
          text: 'PHP',
          level: 60
        },
        {
          text: 'Python',
          level: 50
        },
        {
          text: 'Javascript(jQuery, VueJS)',
          level: 70
        },
        {
          text: 'MySQL, SQL Server, PostgreSQL',
          level: 50
        },
        {
          text: 'CSS3, HTML5, Bootstrap4, Vuetify',
          level: 70
        },
      ],
      languages:[
        {
          text: 'Spanish',
          level: 90
        },
        {
          text: 'English',
          level: 55
        },
      ],
      education:[
        {
          text: 'Colegio de Estudios Científicos y Tecnológicos del Estado de Guanajuato',
          generation: '2012 - 2015',
          specialty: 'Software programmer',
          degree: 'Software Programmer Technician'
        },
        {
          text: 'Instituto Tecnológico de León',
          generation: '2015 – 2019',
          specialty: 'Computer stystems engineer',
          degree: 'Still no degree'
        },
      ],
      experience:[
        {
          period: 'January 2018 – February 2018',
          company: '2904 Marketing and Research',
          job: 'Pollster',
          task: 'Pollster in Guanajuato Pavilion'
        },
        {
          period: 'August 2019 - Present',
          company: 'Infoware',
          job: 'Developer',
          task: 'Development of REST APIs for web applications'
        },
      ],
      soft_skills:['Teamwork', 'Autodidact', 'Adaptive', 'Persistent', 'High responsability level', 'Ability to solve problems'],
      showArrow: false,
    }),
  }
</script>
