<template>
    <v-container>
        <h1 class="text--secondary mb-3 mt-3">My ads</h1>
        <v-card 
    class="elevation-10 mb-5"
    v-for="ad in ads"
    :key="ad.id"
    >
    <v-layout row>
    <v-flex xs4 class="pl-3">
    	<v-img
    	:src="ad.src"
    	height="175px"
    	></v-img>	
    	</v-flex>
    	<v-row>
            <v-card-text>
              <h2 class="text--primary">{{ ad.title }}</h2>
              <p>{{ ad.desc }}</p>
            </v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="primary" variant="text" :to="'/ad/' + ad.id">
                Open
              </v-btn>
              <v-spacer></v-spacer>
            </v-card-actions>
          </v-row>
    </v-layout>
    </v-card>
    </v-container>
</template>


<script>
export default {
    data() {
        return {
                  ads: [
                {
                    title: "First",
                    desc: "First Desc",
                    promo: true,
                    src: "https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg",
                    id: "1",
                            },
                {
                    title: "Second",
                    desc: "Second Desc",
                    promo: true,
                    src: "https://cdn.vuetifyjs.com/images/carousel/sky.jpg",
                    id: "2",
                },
                {
                    title: "Third",
                    desc: "Thitd Desc",
                    promo: true,
                    src: "https://cdn.vuetifyjs.com/images/carousel/bird.jpg",
                    id: "3",
                },
                {
                    title: "Fouth",
                    desc: "Fouth Desc",
                    promo: true,
                    src: "https://cdn.vuetifyjs.com/images/carousel/planet.jpg",
                    id: "4",
                },
            ],

        }
    }
}
</script>

