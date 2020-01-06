<template>
  <v-app>
    <v-row>
      <v-col class="mt-8">
        <v-card class="mx-4 py-1 px-1 grey lighten-2">
          <h1 class="mb-3 teal darken-4 white--text text-center">About me</h1>
          <p class="text-center"><strong>I'm a Developer.</strong></p>
          <p>I am a responsible and persevering developer who likes to learn and use technologies focused on both web development and desktop applications.</p>
          <p>I am passionate about learning, creating and improving my skills to develop software with high quality.</p>
        </v-card>
      </v-col>
    </v-row>
    <v-row style="margin-top: -70px;">
      <v-col cols="5">
        <v-card tile class="ml-4 py-1 px-1 grey lighten-2">
          <h1 class="teal darken-4 white--text text-center">Contact Info</h1>
          <v-list-item v-for="(contact, i) in contacts" :key="i">
                <v-list-item-icon>
                  <v-icon v-text="contact.icon"></v-icon>
                  <span class="ml-3"> {{contact.text}} </span>
                </v-list-item-icon>
          </v-list-item>
        </v-card>
      </v-col>
      <v-col cols="7">
        <v-card tile height="223px" class="mr-4 py-1 px-1 grey lighten-2">
          <h1 class="teal darken-4 white--text text-center">Diplomas</h1>
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
  </v-app>
</template>

<script>
  export default {
    name: 'About',
    data: () => ({
      contacts: [
        { icon: 'mdi-email', text: 'jassojorgealberto@gmail.com' },
        { icon: 'mdi-cellphone-iphone', text: '477 631 84 31' },
        { icon: 'mdi-map-marker', text: 'León GTO México' }
      ],
      diplomas: [
        {
          icon: 'mdi-code-tags',
          text: 'Cédula profesional de Técnico Programador de Software'
        },
        {
          icon: 'mdi-certificate',
          text: 'Acreditación del nivel intermedio del idioma inglés'
        }
      ]
    })
  };
</script>
