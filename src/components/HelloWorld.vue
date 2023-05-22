<template>
  <v-app-bar absolute="" color="white" border height="91" elevation="0">
    <template v-slot:prepend>
      <v-img src="https://cress.gigsalad.com/images/logo.svg" class="ma-5" max-width="60"></v-img>
      <v-menu v-model="menu">
            <template v-slot:activator="{ props }">
              <v-btn text v-bind="props"><span>Menu</span><v-icon size="25" color="blue" 																				icon="mdi-chevron-down"></v-icon> </v-btn>
            </template>
          </v-menu>
    </template>

    <v-divider
      vertical
    ></v-divider>

    <v-app-bar-title>
      <v-text-field v-if="$vuetify.display.lg || $vuetify.display.md || $vuetify.display.xl" elevation="0" prepend-inner-icon="mdi-magnify" variant="plain" placeholder="What kind of talent and service can we help you find?"></v-text-field>
    </v-app-bar-title>

      <v-divider vertical v-if="$vuetify.display.lg || $vuetify.display.md || $vuetify.display.xl"></v-divider>
      <v-btn variant="icon" class="ml-5" size="20" ><v-icon>mdi-magnify</v-icon></v-btn>
      <v-btn variant="icon" class="ml-5" size="20" ><v-icon>mdi-heart-outline</v-icon></v-btn>
      <v-btn variant="text" v-if="$vuetify.display.lg || $vuetify.display.md || $vuetify.display.xl">Log in</v-btn>
      <v-btn color="blue"  variant="flat" class="mr-10" v-if="$vuetify.display.lg || $vuetify.display.md || $vuetify.display.xl">List your services</v-btn>
  </v-app-bar>
  <v-row v-if="menu" class="mt-16">
    <v-col cols="12">
      <v-card>
        <v-row>
        <v-col class="text-center" md="2" lg="2">  
    </v-col>
    <v-col lg="2" md="2" cols="12" class="text-center">
      <v-icon size="40">mdi-music</v-icon>
      <p class="text-subtitle-1 font-weight-medium">Musical Acts</p>
      <p class="text-subtitle-2 font-weight-thin">Bands, DJs, Ensembles, Singers, Soloists, Wedding Musicians, and more</p>
    </v-col>
    <v-col lg="2" md="2" cols="12" class="text-center">
      <v-icon size="40">mdi-music</v-icon>
      <p class="text-subtitle-1 font-weight-medium">Musical Acts</p>
      <p class="text-subtitle-2 font-weight-thin">Bands, DJs, Ensembles, Singers, Soloists, Wedding Musicians, and more</p>
    </v-col>
    <v-col lg="2" md="2" cols="12" class="text-center">
      <v-icon size="40">mdi-music</v-icon>
      <p class="text-subtitle-1 font-weight-medium">Musical Acts</p>
      <p class="text-subtitle-2 font-weight-thin">Bands, DJs, Ensembles, Singers, Soloists, Wedding Musicians, and more</p>
    </v-col>
    <v-col lg="2" md="2" cols="12" class="text-center">
      <v-icon size="40">mdi-music</v-icon>
      <p class="text-subtitle-1 font-weight-medium">Musical Acts</p>
      <p class="text-subtitle-2 font-weight-thin">Bands, DJs, Ensembles, Singers, Soloists, Wedding Musicians, and more</p>
    </v-col>
      <v-col cols="12" class="text-center ma-4">
      <v-divider></v-divider>
        <v-btn class="mt-3 ma-2" flat color="blue" >Quick Quote</v-btn>
        <v-btn class="mt-2 ma-2" variant="text" >Home</v-btn>
        <v-btn class="mt-2 ma-2" variant="text"  >How it works</v-btn>
        <v-btn class="mt-2 ma-2" variant="text"  >Party ideas</v-btn>
        <v-btn class="mt-2 ma-2" variant="text" >about us</v-btn>
        <v-btn class="mt-2 ma-2" variant="text" >Blog</v-btn>
        <v-btn class="mt-2 ma-2" variant="text" >Help Center</v-btn>
      </v-col>
    </v-row>
      </v-card>
    </v-col>
  </v-row>
</template>
<script>

export default {
  name: 'Helloworld',

  data: () => ({
    menu: false,
  }),
}
</script>