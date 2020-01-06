<!-- https://blog.lichter.io/posts/dynamic-images-vue-nuxt/ -->
<template>
  <v-app>
    <div class="resume">
      <v-responsive class="overflow-y-auto" max-height="550">
        <v-row>
          <v-col cols="4">
            <v-card class="mx-4 py-1 px-1 grey lighten-2" max-width="350" tile>
              <h1 class="mb-3 teal darken-4 white--text text-center">Skill</h1>
              <v-list-item v-for="(skill, i) in skills" :key="i">
                <v-list-item-content>
                  <v-list-item-title>
                    <span>{{skill.text}}</span>
                    <v-progress-linear :value="skill.level" class="mt-1" height="7" color="teal darken-4"></v-progress-linear>
                  </v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-card>
          </v-col>
          <v-col cols="8">
            <v-card class="mx-4 py-1 px-1 grey lighten-2" max-width="570" tile>
              <h1 class="mb-3 teal darken-4 white--text text-center">Education</h1>
              <v-timeline>
                <v-timeline-item v-for="(item, i) in education" :key="i" large>
                  <template v-slot:icon>
                    <v-avatar>
                      <img :src="require(`../assets/${item.logo}.png`)">
                      <!--<v-img src="../assets/logo4.png"></v-img>-->
                    </v-avatar>
                  </template>
                  <template v-slot:opposite>
                    <span class="text-center">{{item.text}}</span>
                  </template>
                  <v-card class="elevation-2 ">
                    <p class="text-center"><strong>{{item.generation}}</strong></p>
                    <p class="text-center">{{item.degree}}</p>
                  </v-card>
                </v-timeline-item>
              </v-timeline>
            </v-card>
            <br>
            <v-card class="mx-4 py-1 px-1 grey lighten-2" max-width="570" tile>
              <h1 class="mb-3 teal darken-4 white--text text-center">Soft Skill</h1>
                <v-carousel cycle height="30px" width="100px" :show-arrows="showArrow" hide-delimiters>
                  <v-carousel-item v-for="(skill, i) in soft_skills" :key="i">
                    <v-sheet color="grey lighten-2" height="100%" >
                      <v-row class="fill-height" align="center" justify="center">
                        <span class="black--text">{{ skill }}</span>
                      </v-row>
                    </v-sheet>
                  </v-carousel-item>
                </v-carousel>
            </v-card>
          </v-col>
        </v-row>
        <v-lazy transition="fade-transition">
          <v-row>
            <v-col cols="4">
              <v-card class="mx-4 py-1 px-1 grey lighten-2" max-width="350" tile>
                <h1 class="mb-3 teal darken-4 white--text text-center">Languages</h1>
                <v-list-item v-for="(language, i) in languages" :key="i">
                  <v-list-item-content>
                    <v-list-item-title>
                      <span> {{language.text}} </span>
                      <v-progress-linear :value="language.level" class="mt-1" height="7" color="teal darken-4"></v-progress-linear>
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-card>
            </v-col>
            <v-col cols="8">
              <v-card class="mx-4 py-1 px-1 grey lighten-2" max-width="570" tile>
                <h1 class="mb-3 teal darken-4 white--text text-center">Experience</h1>
                <v-timeline>
                  <v-timeline-item v-for="(item, i) in experience" :key="i" large>
                    <template v-slot:icon>
                      <v-avatar>
                        <img :src="require(`../assets/${item.logo}.png`)">
                      </v-avatar>
                    </template>
                    <template v-slot:opposite>
                      <span class="text-center">{{item.company}}</span>
                    </template>
                    <v-card class="elevation-2 ">
                      <p class="text-center"><strong>{{item.period}}</strong></p>
                      <p class="text-center">{{item.task}}</p>
                    </v-card>
                  </v-timeline-item>
                </v-timeline>
              </v-card>
            </v-col>
          </v-row>
        </v-lazy>
      </v-responsive>
    </div>
  </v-app>
</template>

<script>
  export default {
    name: 'Resume',
    data: () => ({
      skills: [
        { text: 'Ruby, Ruby on Rails', level: 60 },
        { text: 'Java', level: 60 },
        { text: 'PHP', level: 60 },
        { text: 'Python', level: 50 },
        { text: 'Javascript(jQuery, VueJS)', level: 70 },
        { text: 'MySQL, SQL Server', level: 50 },
        { text: 'CSS3, HTML5, Bootstrap4', level: 70 }
      ],
      languages:[
        { text: 'Spanish', level: 90 },
        { text: 'English', level: 55 },
      ],
      education:[
        {
          text: 'Colegio de Estudios Científicos y Tecnológicos del Estado de Guanajuato',
          generation: '2012-2015',
          degree: 'Software Programmer Technician',
          logo: 'logo1'
        },
        {
          text: 'Instituto Tecnológico de León',
          generation: '2015–2019',
          degree: 'Systems engineer',
          logo: 'logo2'
        },
      ],
      experience:[
        {
          period: 'January 2018–February 2018',
          company: '2904 Marketing and Research',
          task: 'Pollster in Guanajuato Pavilion',
          logo: 'logo3'
        },
        {
          period: 'August 2019-Present',
          company: 'Infoware',
          task: 'Development of REST APIs for web applications',
          logo: 'logo4'
        },
      ],
      soft_skills:['Teamwork', 'Autodidact', 'Adaptive', 'Persistent', 'High responsability level', 'Ability to solve problems'],
      showArrow: false
    })
  };
</script>
