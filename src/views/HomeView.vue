<template>
  <section color="grey">
    <HelloWorld />
    <v-row>
      <v-col lg="2"></v-col>
      <v-col class="mt-16" cols="12" lg="4" >
        <v-carousel
          cycle
          interval="4000"
          height="675"
          hide-delimiters
          :show-arrows="false"
        >
          <v-carousel-item
            v-for="(slide, i) in slides"
            transition="fade-transition"
            origin="center center"
            :key="i"
          >
            <v-sheet
              height="100%"
            >
              <div class="d-flex fill-height justify-center align-center">
                <v-img :src="slide"></v-img>
              </div>
            </v-sheet>
          </v-carousel-item>
        </v-carousel>
      </v-col>
      <v-col lg="4" cols="12" align-self="center">
        <h1 class="ma-6 text-h2 font-weight-bold">
          <span style="color:#2690ff;">Book something awesome </span> for your next event
        </h1>
        <p class="ma-6 font-weight-normal">From birthday parties to weddings, we’ll help you book <br> the best talent for any occasion.</p>
      </v-col>
      <v-col cols="2"></v-col>
      <div class="container background-image" v-if="$vuetify.display.lg || $vuetify.display.xl">
      <v-text-field class="overlay-text-field" flat color="blue"  bg-color="#ECEFF1" elevation="0"  prepend-inner-icon="mdi-magnify" placeholder="What kind of talent and service can we help you find?" variant="outlined">
      <template v-slot:append-inner>
        <v-btn color="blue">Search</v-btn>
      </template>
    </v-text-field>
    </div>
    </v-row>
    <v-row v-if="$vuetify.display.md || $vuetify.display.sm">
      <v-col cols="12">
        <v-divider></v-divider>
        <v-text-field flat color="blue"  bg-color="#ECEFF1" elevation="0"  prepend-inner-icon="mdi-magnify" placeholder="What kind of talent and service can we help you find?" variant="outlined"></v-text-field>
      </v-col>
    </v-row>
    <v-row style="background-color:#f7f9fa;">
      <v-col cols="12" class="text-center mt-10">
        <p class="text-h5 font-weight-bold">Whatever you’re planning, <br> make it extraordinary.</p>
      </v-col>
      <v-col cols="12">
        <EventCard :data="EventOne"/>
      </v-col>
      <v-col cols="12">
        <EventCard :data="EventTwo"/>
      </v-col>
      <v-col cols="12">
        <EventCard :data="EventThree"/>
      </v-col>
      <v-col cols="12" class="text-center mt-10">
        <p class="text-h6 font-weight-medium">or </p>
        <br>
        <a href="#" class="text-h6 font-weight-medium" style="color:black;">Browse Event-Specific Vendors</a>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" class="text-center mt-10">
        <p class="text-h5 font-weight-bold">Over 110,000 bands, entertainers, <br> and event services for hire.</p>
      </v-col>
      <v-col lg="2"></v-col>
      <v-col lg="3" cols="12" class="mt-16">
        <v-card
            elevation="0"
          >
            <div class="d-flex flex-no-wrap">
              <v-avatar
                class="ma-3"
                size="125"
                rounded="0"
              >
                <v-img height="50" src="https://cress.gigsalad.com/images/svg/standalone/how-it-works/browse-compare.svg"></v-img>
              </v-avatar>
              <div>
                <v-card-title class="text-h5 mt-6">
                  Browse and compare.
                </v-card-title>
                <p class="text-subtitle-2 ml-4 font-weight-light">Compare rates and availability of local entertainers and vendors.</p>
              </div>
            </div>
          </v-card>
          <v-card
            elevation="0"
          >
            <div class="d-flex flex-no-wrap">
              <v-avatar
                class="ma-3"
                size="125"
                rounded="0"
              >
                <v-img height="50" src="https://cress.gigsalad.com/images/svg/standalone/how-it-works/book-securely.svg"></v-img>
              </v-avatar>
              <div>
                <v-card-title class="text-h5 mt-6">
                  Book securely.
                </v-card-title>
                <p class="text-subtitle-2 ml-4 font-weight-light">Booking through GigSalad ensures payment protection, amazing service, and no-hassle refunds with our Worry-Free Guarantee.</p>
              </div>
            </div>
          </v-card>
          <v-card
            elevation="0"
          >
            <div class="d-flex flex-no-wrap">
              <v-avatar
                class="ma-3"
                size="125"
                rounded="0"
              >
                <v-img height="50" src="https://cress.gigsalad.com/images/svg/standalone/how-it-works/enjoy-event.svg"></v-img>
              </v-avatar>
              <div>
                <v-card-title class="text-h5 mt-6">
                  Enjoy your event.
                </v-card-title>
                <p class="text-subtitle-2 ml-4 font-weight-light">Sit back, relax, and watch your party come to life.</p>
              </div>
            </div>
          </v-card>
      </v-col>
      <v-col cols="12" lg="5" class="mt-8">
        <v-img src="https://cress.gigsalad.com/images/how-it-works-laptop--755w.jpg"></v-img>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" class="text-center">
        <v-btn color="blue" flat size="x-large">Get Started</v-btn>
        <p style="color:#2690ff;" class="mt-5 font-weight-medium">Book something awesome.</p>
      </v-col>
    </v-row>
    <v-row>
      <section>
      <v-col cols="12">
        <ContSlider/>
      </v-col>
    </section>
    </v-row>
    <v-row style="background-color:#f7f9fa;">
      <v-col cols="12" class="text-center mt-16">
        <p class="text-h5 font-weight-bold">Joining GigSalad is quick and easy.</p>
      </v-col>
      <v-col cols="2"></v-col>
      <v-col lg="4" cols="12">
        <v-hover v-slot="{ isHovering, props }">
          <v-card to="#" :elevation="isHovering ? '24':'0'" v-bind="props" >
            <v-icon size="50" :color="isHovering ?'#2690ff':'grey'" class="ml-10 mt-10">mdi-flash</v-icon>
            <v-card-title>
              <p  class="ml-10 ma-5" :style="isHovering ? 'color:#2690ff;':'color:black;'">
                For Gigging Professionals
              </p>
            </v-card-title>
            <v-card-text>
              <v-row>
                <v-col cols="9">
                  <p class="text-subtitle-1 ml-10">Are you a performer, speaker, or event services provider?</p>
                  <br>
                  <p class="text-weight-thin ml-10">GigSalad provides a full-service platform for booking gigs. Get leads, send quotes, and collect payments all in one place.</p>
                </v-col>
                <v-col cols="3">
                  <v-icon class="font-weight-thin" :style="isHovering ? 'color:#2690ff;':'color:black;'" size="50">mdi-chevron-right</v-icon>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-hover>
      </v-col>
      <v-col lg="4" cols="12" class="mb-16">
        <v-hover v-slot="{ isHovering, props }">
          <v-card to="#" :elevation="isHovering ? '24':'0'" v-bind="props" >
            <v-icon size="50" :color="isHovering ?'#2690ff':'grey'" class="ml-10 mt-10">mdi-clipboard-text</v-icon>
            <v-card-title>
              <p  class="ml-10 ma-5" :style="isHovering ? 'color:#2690ff;':'color:black;'">
                For Event Planners
              </p>
            </v-card-title>
            <v-card-text>
              <v-row>
                <v-col cols="9">
                  <p class="text-subtitle-1 ml-10">Are you planning an event and want to hire talent or services?</p>
                  <br>
                  <p class="text-weight-thin ml-10">GigSalad connects you with local vendors and provides a safe and easy platform for booking with a Worry-Free Guarantee.</p>
                </v-col>
                <v-col cols="3">
                  <v-icon class="font-weight-thin" :style="isHovering ? 'color:#2690ff;':'color:black;'" size="50">mdi-chevron-right</v-icon>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-hover>
      </v-col>
    </v-row >
    <v-row>
      <v-col cols="12" class="text-center mt-16">
        <p class="text-h5 font-weight-bold">Millions trust GigSalad to electrify <br> their events.</p>
      </v-col>
      <v-col lg="2"></v-col>
      <v-col lg="2" class="mt-16" cols="12" md="3" sm="6">
        <v-img height="30" src="https://cress.gigsalad.com/images/testimonials/logo--americas-got-talent--106w.png"></v-img>
      </v-col>
      <v-col lg="2" class="mt-16" cols="12" md="3" sm="6">
        <v-img height="30" src="https://cress.gigsalad.com/images/testimonials/logo--nbc--49w.png"></v-img>
      </v-col>
      <v-col lg="2" class="mt-16" cols="12" md="3" sm="6">
        <v-img height="30" src="https://cress.gigsalad.com/images/testimonials/logo--macys--151w.png"></v-img>
      </v-col>
      <v-col lg="2" class="mt-16" cols="12" md="3" sm="6">
        <v-img height="30" src="https://cress.gigsalad.com/images/testimonials/logo--cbs--84w.png"></v-img>
      </v-col>
      <v-col lg="2" cols="12" md="3" sm="6">
      </v-col>
      <v-col lg="2"></v-col>
      <v-col lg="2" class="mt-16" cols="12" md="3" sm="6">
        <v-img height="30"  src="https://cress.gigsalad.com/images/testimonials/logo--microsoft--188w.png"></v-img>
      </v-col>
      <v-col lg="2" class="mt-16" cols="12" md="3" sm="6">
        <v-img height="30" src="https://cress.gigsalad.com/images/testimonials/logo--mtv--66w.png"></v-img>
      </v-col>
      <v-col lg="2" class="mt-16" cols="12" md="3" sm="6">
        <v-img height="30" src="https://cress.gigsalad.com/images/testimonials/logo--mcdonalds--52w.png"></v-img>
      </v-col>
      <v-col lg="2" class="mt-16 mb-16" cols="12" md="3" sm="6">
        <v-img height="30" src="https://cress.gigsalad.com/images/testimonials/logo--volcom--207w.png"></v-img>
      </v-col>
      <v-col lg="2" cols="12" md="3" sm="6">
      </v-col>
    </v-row>
  </section>
  <v-row>
    <v-col cols="12">
      <Footer/>
    </v-col>
  </v-row>
</template>

<script>
import { defineComponent } from 'vue';

// Components
import HelloWorld from '../components/HelloWorld.vue';
import EventCard from '../components/EventCard.vue';
import ContSlider from '../components/ContSlider.vue';
import Footer from '../components/Footer.vue';

export default defineComponent({
  name: 'HomeView',

  components: {
    HelloWorld,
    EventCard,
    ContSlider,
    Footer
  },
  data() {
    return {
        slides: [
          'https://cress.gigsalad.com/images/portraits/princess--421w.jpg',
          'https://cress.gigsalad.com/images/portraits/santa--421w.jpg',
          'https://cress.gigsalad.com/images/portraits/caterer--421w.jpg',
          'https://cress.gigsalad.com/images/portraits/rock-band--421w.jpg',
        ],
        EventOne: {
          title: 'Musical Acts',
          dataArray:[
            {
              title: 'Bands & Groups',
              subtitle: 'Blues Bands, Mariachis, Wedding Bands...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/BandsGroups.jpg',
            },
            {
              title: 'Singers',
              subtitle: 'Country Singers, Singing, Guitarists, Rappers...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/Singers.jpg',
            },
            {
              title: 'Ensembles',
              subtitle: 'Chamber Orchestras, Classical Ensembles, String Trios...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/Ensembles.jpg',
            },
            {
              title: 'Solo Musicians',
              subtitle: 'Bagpipers, Guitarists, Pianists, Violinists...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/SoloMusicians.jpg',
            },
            {
              title: 'DJs',
              subtitle: 'Bar Mitzvah DJs, Prom DJs, Wedding DJs...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/DJs.jpg',
            }
          ]
        },
        EventTwo: {
          title: 'Entertainers',
          dataArray:[
            {
              title: 'Actors & Speakers',
              subtitle: 'Actors, Emcees, Keynote Speakers...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/ActorsSpeakers.jpg',
            },
            {
              title: 'Children’s Parties',
              subtitle: 'Costumed Characters, Face Painters, Petting Zoos...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/BitmapChildrensParties.jpg',
            },
            {
              title: 'Circus & Acrobatic',
              subtitle: 'Comedy Shows, Stand-Up Comedians...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/CircusAcrobatic.jpg',
            },
            {
              title: 'Comedians',
              subtitle: 'Bagpipers, Guitarists, Pianists, Violinists...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/Comedians.jpg',
            },
            {
              title: 'Dance',
              subtitle: 'Ballet, Burlesque, Flamenco, Hula...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/Dance.jpg',
            }
          ]
        },
        EventThree: {
          title: 'Event Services',
          dataArray:[
            {
              title: 'Beauty',
              subtitle: 'Hair Stylists, Makeup Artists, Mobile Spas...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/ProfessionalServices.jpg',
            },
            {
              title: 'Food & Beverage',
              subtitle: 'Bartenders, Caterers, Waitstaff...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/FoodDrink.jpg',
            },
            {
              title: 'Outdoor Parties',
              subtitle: 'Carnival Games, Inflatables, Petting Zoos...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/OutdoorParties.jpg',
            },
            {
              title: 'Photo & Video',
              subtitle: 'Photographers, Videographers...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/PhotoVideo.jpg',
            },
            {
              title: 'Rentals & Supplies',
              subtitle: 'Costumes, Party Rentals, Photo Booths...',
              image: 'https://cress.gigsalad.com/images/home-slider-categories/RentalsSupplies.jpg',
            }
          ]
        }
    }
  },
});
</script>

<style>
.containers {
  position: relative;
  display: inline-block;
}

.background-image {
  width: 100%;
  height: auto;
}
.overlay-text-field {
  position: absolute;
  top:15%;
  left: 50%;
  opacity: 0.9;
  transform: translate(-50%, -50%);
  z-index: 1;
  width: 1160px; /* Set the width of the text field as needed */
  height: 80px;
}
</style>