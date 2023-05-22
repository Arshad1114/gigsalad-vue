<template>
  <v-row>
    <v-col cols="12" class="text-center">
        <p class="text-h6 font-weight-bold">{{ $props.data.title }}</p>
    </v-col>
    <v-col lg="2"></v-col>
      <v-col lg="8">
        <v-slide-group
        v-model="model"
        show-arrows
      >
        <v-slide-group-item
          v-for="(item,n) in $props.data.dataArray"
          :key="n"
        >
        <div class="flip-card">
          <div class="flip-card-inner">
            <v-card
            color="grey-lighten-1"
            :class="['ma-2', 'flip-card-front']"
            width="275"
          >
            <v-img :src="item.image" gradient="rgba(0,0,0,.1), rgba(0,0,0,.8)">
              <v-row class="fill-height mt-16" align="center" >
                <v-col cols="12" class="text-center">
                  <p style="color:white;" class="text-subtitle-1 font-weight-black">{{item.title}}</p>
                  <p style="color:white;" class="text-subtitle-2 text-center font-weight-medium">{{item.subtitle}}</p>
                </v-col>
              </v-row>
            </v-img>
          </v-card>
          <v-card  width="275" height="300" class="ma-2 flip-card-back" elevation="0">
            <v-card-title class="text-h6" ><span >Solo Musicians</span></v-card-title>
            <v-card-text>
                  <v-list class="overflow-y-auto" style="height: 150px">        
                        <p v-for="(item, i) in links" :key="i" class="text-center" style="color:#2690ff;">{{item}}</p>
                    </v-list>
            </v-card-text>
            <v-card-actions>
               <v-btn block variant="text" color="#2690ff">View All solo musician</v-btn></v-card-actions>
          </v-card>
          </div>
        </div>
        </v-slide-group-item>
      </v-slide-group>
    </v-col>
  </v-row>
</template>
<script>
export default {
  name: 'EventCard',
  props: ['data'],
  data: () => ({
    menu: false,
    toggle:true,
    links: [
      'Bagpipers',
      'Dueling Pianos',
      'Guitarists',
      'Harpists',
      'Pianists',
      'Singing Guitarists',
      'Singing Pianists',
      'Steel Drum Players',
      'Violinists',
      'Wedding Musicians'
    ]
  }),
}
</script>
<style>
.flip-card {
  background-color: transparent;
  width: 300px;
  height: 300px;
  perspective: 1000px;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 1.0s;
  transform-style: preserve-3d;
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 90%;
  height: 90%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: #bbb;
}

.flip-card-back {
  color: black;
  transform: rotateY(180deg);
}
</style>