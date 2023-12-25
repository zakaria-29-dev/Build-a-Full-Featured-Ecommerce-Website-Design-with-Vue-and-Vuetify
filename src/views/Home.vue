<template>
  <v-app :style="{ background: $vuetify.theme.themes.light.colors.primary }">
    <v-main>
      <SideBare />
      <v-container fluid>
        <v-row>
          <v-col cols="12" sm="2">
            <v-row>
              <v-col cols="12" sm="12">
                <v-expansion-panels v-model="panel">
                  <v-expansion-panel class="co">
                    <v-expansion-panel-title class="text-white bg-orange"
                      ><v-icon icon="mdi mdi-menu" class="ml-n4 mr-1"> </v-icon
                      >Category</v-expansion-panel-title
                    >
                    <v-expansion-panel-text>
                      <v-list class="cat" density="compact">
                        <v-list-item
                          v-for="(item, i) in items"
                          :key="i"
                          :value="item"
                          color="orange"
                          variant="plain"
                          class="ml-n2"
                        >
                          <v-list-item-title
                            v-text="item.text"
                            class="text-caption"
                          ></v-list-item-title>
                        </v-list-item>
                      </v-list>
                    </v-expansion-panel-text>
                  </v-expansion-panel>
                </v-expansion-panels>
              </v-col>
              <v-col cols="12" sm="12">
                <v-card class="co">
                  <v-list lines="two" class="cat pro">
                    <v-list-subheader inset class="ml-n10 text-white"
                      >Hot Products</v-list-subheader
                    >

                    <v-list-item
                      v-for="product in products"
                      :key="product.title"
                      :title="product.title"
                      color="red"
                    >
                      <v-list-item-subtitle
                        v-text="product.subtitle"
                        class="text-caption text-orange"
                      ></v-list-item-subtitle>
                      <template v-slot:prepend>
                        <v-avatar variant="outlined" rounded="0" color="grey">
                          <v-img color="white" :src="product.image"></v-img>
                        </v-avatar>
                      </template>
                    </v-list-item>
                  </v-list>
                </v-card>
              </v-col>
              <v-col cols="12" sm="12">
                <v-card class="co pa-2">
                  <h5 class="ml-4 text-white">Tag Cloud</h5>
                  <v-chip class="ma-2 tag" label color="white">
                    Desserts
                  </v-chip>
                  <v-chip class="ma-2" label color="white"> Drinks </v-chip>
                  <v-chip class="ma-2" label color="white"> Pasta </v-chip>
                  <v-chip class="ma-2" label color="white"> Pizza </v-chip>
                  <v-chip class="ma-2" label color="white"> Sandwiches </v-chip>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="12" sm="8">
            <v-row>
              <v-col cols="12" sm="12">
                <v-carousel :show-arrows="false">
                  <v-carousel-item
                    v-for="(item, i) in pictures"
                    :key="i"
                    :src="item.src"
                    cover
                  ></v-carousel-item>
                </v-carousel>
              </v-col>
              <v-col cols="12" sm="12">
                <v-toolbar color="#1F1F1F">
                  <v-toolbar-title
                    >Safe and on time home deliveries</v-toolbar-title
                  >

                  <v-spacer></v-spacer>

                  <v-btn color="white" class="btn"> View Offers </v-btn>
                </v-toolbar>
              </v-col>
              <v-col cols="12" sm="12">
                <v-card class="tb" flat>
                  <v-tabs v-model="tab" color="grey" align-tabs="end">
                    <v-tab :value="1">Desserts</v-tab>
                    <v-tab :value="2">Drinks</v-tab>
                    <v-tab :value="3">Pasta</v-tab>
                  </v-tabs>
                  <v-window v-model="tab" class="co">
                    <v-window-item v-for="n in 3" :key="n" :value="n">
                      <v-container fluid>
                        <v-row>
                          <v-col
                            v-for="(dishe, i) in dishes"
                            :key="i"
                            cols="12"
                            md="3"
                          >
                            <v-hover
                              v-slot="{ isHovering, props }"
                              open-delay="200"
                            >
                              <v-card class="" color="#111111" v-bind="props">
                                <v-img
                                  height="90"
                                  :src="dishe.image"
                                  class="mt-6"
                                ></v-img>
                                <v-card-item class="text-center mt-14">
                                  <v-card-subtitle>
                                    <span class=" ">{{ dishe.name }}</span>
                                  </v-card-subtitle>
                                  <v-card-title
                                    class="text-caption text-orange"
                                    >{{ dishe.money }}</v-card-title
                                  >
                                </v-card-item>
                                <v-expand-transition>
                                  <div
                                    v-if="isHovering"
                                    class="d-flex transition-fast-in-fast-out bg-grey-darken-3 v-card--reveal text-h2"
                                    style="height: 100%"
                                  >
                                    <v-btn
                                      density="compact"
                                      icon="mdi mdi-magnify"
                                      class="mr-2"
                                    ></v-btn>
                                    <v-btn
                                      density="compact"
                                      icon="mdi mdi-heart-outline"
                                      class="mr-2"
                                    ></v-btn>
                                    <v-btn
                                      density="compact"
                                      icon="mdi mdi-sync"
                                    ></v-btn>
                                  </div>
                                </v-expand-transition>
                              </v-card>
                            </v-hover>
                          </v-col>
                          <v-toolbar color="transparent">
                            <v-toolbar-title class="text-white"
                              >Product List</v-toolbar-title
                            >
                            <v-spacer></v-spacer>
                            <v-icon icon="mdi mdi-chevron-left-circle"></v-icon>
                            <v-icon
                              icon="mdi mdi-chevron-right-circle"
                              class=""
                            ></v-icon>
                          </v-toolbar>
                          <v-col cols="12" sm="12">
                            <v-sheet
                              class="mx-auto co"
                              elevation="8"
                              max-width="800"
                            >
                              <v-slide-group
                                v-model="model"
                                class="pa-4"
                                center-active
                                show-arrows
                              >
                                <v-slide-group-item
                                  v-for="(dishe, i) in dishes"
                                  :key="i"
                                  v-slot="{ isSelected, toggle }"
                                >
                                  <v-card
                                    :color="isSelected ? 'primary' : '#111111'"
                                    class="ma-4 btn"
                                    height="100"
                                    width="200"
                                    @click="toggle"
                                  >
                                    <v-row>
                                      <v-col cols="12" sm="6">
                                        <v-img
                                          height="100"
                                          :src="dishe.image"
                                          class="ml-5"
                                        ></v-img>
                                      </v-col>
                                      <v-col
                                        cols="12"
                                        sm="6"
                                        class="text-center mt-6"
                                      >
                                        <span class=" ">{{ dishe.name }}</span>

                                        <h5 class="text-caption text-orange">
                                          {{ dishe.money }}
                                        </h5>
                                      </v-col>
                                    </v-row>
                                    <div
                                      class="d-flex fill-height align-center justify-center"
                                    >
                                      <v-scale-transition>
                                        <v-icon
                                          v-if="isSelected"
                                          color="white"
                                          size="48"
                                          icon="mdi-close-circle-outline"
                                        ></v-icon>
                                      </v-scale-transition>
                                    </div>
                                  </v-card>
                                </v-slide-group-item>
                              </v-slide-group>
                            </v-sheet>
                          </v-col>
                        </v-row>
                      </v-container>
                    </v-window-item>
                  </v-window>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="12" sm="2">
            <v-row>
              <v-col cols="12" sm="12">
                <v-card class="co">
                  <v-list lines="two" class="cat pro">
                    <v-list-item
                      v-for="offer in offers"
                      :key="offer.title"
                      :title="offer.title"
                      color="red"
                    >
                      <v-list-item-subtitle
                        v-text="offer.subtitle"
                        class="text-caption"
                      ></v-list-item-subtitle>
                      <template v-slot:prepend>
                        <v-icon
                          :icon="offer.icon"
                          large
                          color="orange"
                        ></v-icon>
                      </template>
                    </v-list-item>
                  </v-list>
                </v-card>
              </v-col>
              <v-col cols="12" sm="12">
                <v-card class="co pa-2">
                  <div class="float-sm-left">
                    <span class="ml-4 text-white">Tag Cloud</span>
                    <v-icon
                      icon="mdi mdi-chevron-right-circle"
                      class="ml-10"
                    ></v-icon>
                    <v-icon icon="mdi mdi-chevron-left-circle"></v-icon>
                  </div>
                  <div class="text-center">
                    <v-avatar variant="outlined" color="white" class="mt-2">
                      <v-img src="/20.jpg" alt="John"></v-img>
                    </v-avatar>
                    <h5 class="text-grey mt-3">Sabina</h5>
                    <p class="text-grey mt-2 text-caption">
                      Vivamus arcu feils bibendum ut tristique et egestas . eu
                      sem integer vitae justoe eget magna fermentum
                    </p>
                  </div>
                </v-card>
              </v-col>
              <v-col cols="12" sm="12">
                <v-card class="co pa-2">
                  <div class="float-sm-left mb-4">
                    <span class="ml-4 text-white">Latest News </span>
                    <v-icon
                      icon="mdi mdi-chevron-right-circle"
                      class="ml-6"
                    ></v-icon>
                    <v-icon icon="mdi mdi-chevron-left-circle"></v-icon>
                  </div>
                  <div class="text-center">
                    <v-img src="/40.jpg" alt="pi" width="200"></v-img>
                  </div>
                  <h5 class="text-grey mt-3">Purus non enim praesent</h5>
                  <p class="text-grey mt-2 text-caption">July 30, 2020</p>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
    <Footer />
  </v-app>
</template>

<script setup>
import SideBare from "@/components/SideBare.vue";
import Footer from "@/components/Footer.vue";
</script>
<script>
export default {
  data: () => ({
    panel: [0],
    disabled: false,
    tab: null,
    model: null,
    items: [
      { text: "Desserts" },
      { text: "Drinks" },
      { text: "Pasta" },
      { text: "Pizza" },
      { text: "Sandwiches" },
    ],
    products: [
      {
        title: "Pizza",
        subtitle: "$800.00",
        image: "3.png",
      },
      {
        title: "Cheese",
        subtitle: "$300.00",
        image: "11.png",
      },
      {
        title: "Drink",
        subtitle: "$200.00",
        image: "20.png",
      },
      {
        title: "Drink2",
        subtitle: "$180.00",
        image: "21.png",
      },
      {
        title: "Dessert",
        subtitle: "$120.00",
        image: "7.png",
      },
    ],
    offers: [
      {
        title: "Join Risk Free",
        subtitle: "30 days refund ",
        icon: "mdi mdi-diamond-stone",
      },
      {
        title: "100% SAfe",
        subtitle: "Secure Shopping",
        icon: "mdi mdi-anchor",
      },
      {
        title: "24x7 Support",
        subtitle: "Online 24 hours",
        icon: "mdi mdi-coffee",
      },
      {
        title: "Best Offers",
        subtitle: "Grab Now",
        icon: "mdi mdi-basket",
      },
      {
        title: "Free Shiping",
        subtitle: "On all order over",
        icon: "mdi mdi-airplane",
      },
    ],
    pictures: [
      {
        src: "p2.jpg",
      },
      {
        src: "p4.jpg",
      },
      {
        src: "p3.jpg",
      },
      {
        src: "p1.jpg",
      },
    ],
    dishes: [
      { image: "f1.png", name: "Plat unique", money: "$10.00" },
      { image: "f2.png", name: "Plat africains", money: "$25.00" },
      { image: "f3.png", name: "Plat de viand", money: "$15.00" },
      { image: "f4.png", name: "Rajthan", money: "$23.00" },
      { image: "f5.png", name: "The messy house", money: "$10.00" },
      { image: "f6.png", name: "The frenchy", money: "$25.00" },
      { image: "f7.avif", name: "Resse", money: "$15.00" },
      { image: "44.png", name: "Gratin", money: "$23.00" },
    ],
  }),
};
</script>
<style scoped>
.co {
  background-color: #1f1f1f;
}
.tb {
  background-color: #2f2f2f;
}

.cat {
  background-color: #1f1f1f;
  color: white;
}
.tag:hover {
  color: orange;
}
.btn {
  background-color: #111111;
}
.v-card--reveal {
  align-items: center;
  bottom: 0;
  justify-content: center;
  opacity: 0.9;
  position: absolute;
  width: 100%;
}
</style>
