<template>
  <v-app>
    <div class="about">
      <v-row>
        <v-col class="mt-12">
          <v-card class="mx-auto mt-5 px-5" max-width="99%">
            <p>I am Web Developer.</p>
            <p>Full Stack developer, mainly focussed on Web applications, but still experienced with desktop apps. Passionate about learning, teaching, creating software and music.</p>
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="5">
          <v-card max-width="350" tile>
            <h1 class="text-center">Contact Info</h1>
            <v-list-item v-for="(contact, i) in contacts" :key="i">
              <v-list-item-content>
                <v-list-item-title>
                  <v-list-item-icon>
                    <v-icon v-text="contact.icon"></v-icon>
                    <span class="ml-3"> {{contact.text}} </span>
                  </v-list-item-icon>
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-card>
        </v-col>
        <v-col cols="7">
          <v-card max-width="525" tile>
            <h1 class="text-center">Diplomas</h1>
            <v-list-item v-for="(diploma, i) in diplomas" :key="i">
              <v-list-item-content>
                <v-list-item-title>
                  <v-list-item-icon>
                    <v-icon v-text="diploma.icon"></v-icon>
                    <span class="ml-3"> {{diploma.text}} </span>
                  </v-list-item-icon>
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
    name: 'home',
    components: {

    },
    data: () => ({
      contacts: [
        {
          icon: 'mdi-email',
          text: 'jassojorgealberto@gmail.com',
        },
        {
          icon: 'mdi-cellphone-iphone',
          text: '477 631 84 31',
        },
        {
          icon: 'mdi-map-marker',
          text: 'León GTO México',
        },
      ],
      diplomas: [
        {
          icon: 'mdi-code-tags',
          text: 'Cédula profesional de Técnico en Programador de Software',
        },
        {
          icon: 'mdi-certificate',
          text: 'Acreditación del nivel intermedio del idioma inglés',
        },
      ],
    }),
  }
</script>
