<template>
  <v-footer color="#1F1F1F" class="d-flex flex-column">
    <div class="px-4 py-2 bgTop  w-100">
      <v-toolbar color="transparent" height="40">
       <span class="mr-2">Refund Policy</span>
       <span>Privacy Policy</span>
       <v-spacer></v-spacer>
       <v-icon>mdi mdi-cash-multiple</v-icon>
       <v-icon>mdi mdi-currency-usd</v-icon>
       <v-icon>mdi mdi-cash-100</v-icon>
      </v-toolbar>
    </div>
    <div class=" d-flex w-100 bgMidum px-4 pb-10">
<v-row>
  <v-col col="12" sm="3">
    <h4 class="mt-2">Connect With us</h4>
    <span class="text-caption">Facebook</span><br>
    <span class="text-caption">Twitter</span><br>
    <span class="text-caption">Instagram</span><br>
    <span class="text-caption">Whatsapp</span><br>
    <span class="text-caption">Youtube</span><br>
    <span class="text-caption">Pinterest</span>
  </v-col>
  <v-col col="12" sm="3">
    <h4 class="mt-2">More About Store</h4>
    <span class="text-caption">Multiple Branches</span><br>
    <span class="text-caption">Take Franchise</span><br>
    <span class="text-caption">Scheduled Offres</span><br>
    <span class="text-caption">Visit Kitchen</span><br>
    <span class="text-caption">Meet Our Team</span><br>
    <span class="text-caption">More Links</span>
  </v-col>
  <v-col col="12" sm="3">
    <h4 class="mt-2">Offline Store</h4>
    <span class="text-caption">Address :3548 Columbia</span><br>
    <span class="text-caption">Wheeling, West Virginia</span><br>
    <span class="text-caption">26003</span><br>
    <span class="text-caption">Contact: 304-559-3029</span><br>
    <span class="text-caption">304-650-2694</span><br>
    <span class="text-caption">Email: aaeidapro@gmail.com</span>
  </v-col>
  <v-col col="12" sm="3">
    <h4 class="mt-2">Location</h4>
    <v-img src="/map.webp" height="150" class="ml-n16"></v-img>
  </v-col>
</v-row>
    </div>

    <div class="px-4 py-2 bgTop text-center w-100">
      <v-icon class="mr-2">mdi mdi-copyright</v-icon>{{ new Date().getFullYear() }} — <strong>AAE IdeaPro</strong>
    </div>

    </v-footer>
  </template>

  <script>
  export default {};
  </script>

  <style>

.v-footer {
  padding: 0 0 !important;
}
.bgTop{
  background-color:#111111;
}
.bgMidum{
  background-color:#1F1F1F;
}
</style>
