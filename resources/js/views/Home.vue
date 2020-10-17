<template>
  <div>
    <v-app-bar
      dark
    >
      <v-icon large color="success" class="mx-3">mdi-phone-in-talk</v-icon>
      <span class="text-h5">0800 123456789</span>

      <v-spacer></v-spacer>

      <v-btn icon href="#">
        <v-icon large color="success" class="mx-3">mdi-twitter</v-icon>
      </v-btn>
      <v-btn icon href="#">
        <v-icon large color="primary" class="mx-3">mdi-facebook</v-icon>
      </v-btn>
      <v-btn icon href="#">
        <v-icon large color="purple lighten-1" class="mx-3">mdi-instagram</v-icon>
      </v-btn>
      <v-btn icon href="#">
        <v-icon large color="info" class="mx-3">mdi-linkedin</v-icon>
      </v-btn>
      <v-btn icon href="#">
        <v-icon large color="error" class="mx-3">mdi-youtube</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <v-toolbar class="py-auto" style="height: 120px">
        <v-container fluid class="ma-0 pa-5">
          <v-row>
            <v-col cols="4">
              <v-row>
                <span color="black" text class="text-h3 font-weight-black">
                  UNIEX COURIERS
                </span>
              </v-row>

              <v-row>
                <span color="black" text class="text-h5">
                  Delivering across the globe
                </span>
              </v-row>
            </v-col>

            <v-col cols="4">
              <v-row>
                <v-col cols="6">
                  <v-btn text class="text-h4 font-weight-black mx-auto">FIND QUOTE</v-btn>
                </v-col>
                <v-col cols="6">
                  <v-btn text class="text-h4 font-weight-black mx-auto">OUT SERVICES</v-btn>
                </v-col>
              </v-row>
            </v-col>

            <v-col cols="4">
              <v-row justify="end">
                <a href="#">
                  <v-icon class="text-h2">mdi-map-marker</v-icon>
                </a>
                <a href="#">
                  <v-icon class="text-h2">mdi-magnify</v-icon>
                </a>
                <a href="#">
                  <v-icon class="text-h2">mdi-account</v-icon>
                </a>
              </v-row>
            </v-col>
          </v-row>
        </v-container>

      </v-toolbar>

      <v-carousel hide-delimiters>
        <v-carousel-item
          v-for="(item,i) in items"
          :key="i"
          :src="item.src"
        ></v-carousel-item>


      </v-carousel>

      <v-card outlined class="mx-12" style="margin-top: -200px" height="180">
        <div class="row pa-5">
          <div class="col-10">
            <div class="row">
              <div class="col">
                <div class="text-h4 green--text text--darken-2 mb-5">Loading Date</div>
                  <div class="mt-5">
                    <v-menu
                      ref="menu"
                      v-model="menu"
                      :close-on-content-click="false"
                      :return-value.sync="date"
                      transition="scale-transition"
                      offset-y
                      min-width="290px"
                    >
                      <template v-slot:activator="{ on, attrs }">
                        <v-text-field
                          solo
                          v-model="date"
                          label="Picker in menu"
                          prepend-icon="mdi-calendar"
                          readonly
                          v-bind="attrs"
                          v-on="on"
                        ></v-text-field>
                      </template>
                      <v-date-picker
                        v-model="date"
                        no-title
                        scrollable
                      >
                        <v-spacer></v-spacer>
                        <v-btn
                          text
                          color="primary"
                          @click="menu = false"
                        >
                          Cancel
                        </v-btn>
                        <v-btn
                          text
                          color="primary"
                          @click="$refs.menu.save(date)"
                        >
                          OK
                        </v-btn>
                      </v-date-picker>
                    </v-menu>
                  </div>
              </div>
              <div class="col">
                <div class="text-h4 green--text text--darken-2 mb-5">Pickup Location</div>
                  <div class="mt-5">
                    <v-text-field
                      solo
                      full-width
                    >
                    </v-text-field>
                  </div>
              </div>
              <div class="col">
                <div class="text-h4 green--text text--darken-2 mb-5">Drop-off Location</div>
                  <div class="mt-5">
                    <v-text-field
                      solo
                      full-width
                    >
                    </v-text-field>
                  </div>
              </div>
            </div>
          </div>

          <div class="col-2">
            <v-btn large color="success" class="ma-auto">
              Proceed
            </v-btn>
          </div>
        </div>

      </v-card>

      <v-container style="height: 160px">
        <v-row>
          <v-col>
            <v-row justify="center">
              <v-icon class="text-h1">mdi-truck</v-icon>
            </v-row>
            <v-row justify="center">
              <span class="text-subtitle-1">
                FREIGHT & PARCELS
              </span>
            </v-row>
          </v-col>
          <v-col>
            <v-row justify="center">
              <v-icon class="text-h1">mdi-car-battery</v-icon>
            </v-row>
            <v-row justify="center">
              <span class="text-subtitle-1">
                AUTOMOTIVES
              </span>
            </v-row>
          </v-col>
          <v-col>
            <v-row justify="center">
              <v-icon class="text-h1">mdi-cogs</v-icon>
            </v-row>
            <v-row justify="center">
              <span class="text-subtitle-1">
                MACHINERY
              </span>
            </v-row>
          </v-col>
          <v-col>
            <v-row justify="center">
              <v-icon class="text-h1">mdi-sofa</v-icon>
            </v-row>
            <v-row justify="center">
              <span class="text-subtitle-1">
                FURNITURE
              </span>
            </v-row>
          </v-col>
          <v-col>
            <v-row justify="center">
              <v-icon class="text-h1">mdi-motorbike</v-icon>
            </v-row>
            <v-row justify="center">
              <span class="text-subtitle-1">
                MOTORCYCLE
              </span>
            </v-row>
          </v-col>
          <v-col>
            <v-row justify="center">
              <v-icon class="text-h1">mdi-medical-bag</v-icon>
            </v-row>
            <v-row justify="center">
              <span class="text-subtitle-1">
                MEDICAL
              </span>
            </v-row>
          </v-col>
        </v-row>
      </v-container>

      <v-container style="height: 260px">
        <v-row>
          <v-col>
            <v-row justify="center">
              <v-img
                max-height="100px"
                max-width="220px"
                src="https://picsum.photos/id/11/500/300"
              ></v-img>
            </v-row>
            <v-row justify="center">
              <span class="text-h5">
                FTL Freight Shipping
              </span>
            </v-row>
          </v-col>
          <v-col>
            <v-row justify="center">
              <v-img
                max-height="100px"
                max-width="220px"
                src="https://picsum.photos/id/11/500/300"
              ></v-img>
            </v-row>
            <v-row justify="center">
              <span class="text-h5">
                LTL Freight Shipping
              </span>
            </v-row>
          </v-col>
          <v-col>
            <v-row justify="center">
              <v-img
                max-height="100px"
                max-width="220px"
                src="https://picsum.photos/id/11/500/300"
              ></v-img>
            </v-row>
            <v-row justify="center">
              <span class="text-h5">
                Documents & Parcels
              </span>
            </v-row>
          </v-col>
          <v-col>
            <v-row justify="center">
              <v-img
                max-height="100px"
                max-width="220px"
                src="https://picsum.photos/id/11/500/300"
              ></v-img>
            </v-row>
            <v-row justify="center">
              <span class="text-h5">
                International
              </span>
            </v-row>
          </v-col>
        </v-row>
      </v-container>

      <v-container>

      </v-container>

      <v-container fluid style="height: 120px" class="success px-10">
        <v-row>
          <v-col cols="5">
            <span class="text-h4 text-light float-right">
              Get Your Shipping Quote
            </span>
          </v-col>
          <v-col cols="5">
            <v-text-field
              solo
            >
            </v-text-field>
          </v-col>
          <v-col cols="2">
            <v-btn success>
              Start Quoting
            </v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        login_menu: false,
        tab: null,
        items: [
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
          },
        ],
        date: new Date().toISOString().substr(0, 10),
        menu: false,
      }
    },
  }
</script>
