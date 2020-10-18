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
      <div>
        <v-container fluid fill-height>
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

            <v-col cols="5">
              <v-row>
                <v-col cols="6">
                  <v-btn text large class="text-h4 font-weight-black mx-auto">FIND QUOTE</v-btn>
                </v-col>
                <v-col cols="6">
                  <v-btn text large class="text-h4 font-weight-black mx-auto">OUT SERVICES</v-btn>
                </v-col>
              </v-row>
            </v-col>

            <v-col cols="3">
              <v-row justify="end">
                <v-btn fab x-large class="mx-2">
                  <v-icon>mdi-map-marker</v-icon>
                </v-btn>
                <v-btn fab x-large class="mx-2">
                  <v-icon>mdi-magnify</v-icon>
                </v-btn>
                <SignIn class="mx-2"></SignIn>
              </v-row>
            </v-col>
        </v-container>
      </div>

      <v-carousel hide-delimiters>
        <v-carousel-item
          v-for="(item,i) in items"
          :key="i"
          :src="item.src"
        ></v-carousel-item>

        <v-card outlined light class="white mx-12 px-12" style="margin-top: -240px;">
          <v-container fluid fill-height>
            <v-row>
              <v-col cols="10">
                <v-row>
                  <v-col>
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
                  </v-col>
                  <v-col>
                    <div class="text-h4 green--text text--darken-2 mb-5">Pick-Up Location</div>
                    <div class="mt-5">
                      <v-text-field
                        solo
                        label="City and Postal Code"
                      >
                      </v-text-field>
                    </div>
                  </v-col>
                  <v-col>
                    <div class="text-h4 green--text text--darken-2 mb-5">Drop-Off Location</div>
                    <div class="mt-5">
                      <v-text-field
                        solo
                        label="City and Postal Code"
                      >
                      </v-text-field>
                    </div>
                  </v-col>
                </v-row>
              </v-col>

              <v-col>
                <v-container fill-height>
                  <v-row justify="center">
                    <v-btn
                      x-large
                      color="success"
                    >
                      Proceed
                    </v-btn>
                  </v-row>
                </v-container>
              </v-col>
            </v-row>
          </v-container>
        </v-card>
      </v-carousel>



      <v-container fluid class="blue-grey lighten-4">
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

      <v-container fluid>
        <v-row>
          <v-col cols="3">
            <div>
              <v-img
                width="90%"
                max-width="90%"
                class="mx-auto"
                src="https://picsum.photos/id/11/500/300"
              ></v-img>
            </div>
            <div class="text-center">
              <span class="text-h5">
                FTL Freight Shipping
              </span>
            </div>
          </v-col>
          <v-col cols="3">
            <div>
              <v-img
                width="90%"
                max-width="90%"
                class="mx-auto"
                src="https://picsum.photos/id/11/500/300"
              ></v-img>
            </div>
            <div class="text-center">
              <span class="text-h5">
                LTL Freight Shipping
              </span>
            </div>
          </v-col>
          <v-col cols="3">
            <div>
              <v-img
                width="90%"
                max-width="90%"
                class="mx-auto"
                src="https://picsum.photos/id/11/500/300"
              ></v-img>
            </div>
            <div class="text-center">
              <span class="text-h5">
                Documents & Parcels
              </span>
            </div>
          </v-col>
          <v-col cols="3">
            <div>
              <v-img
                width="90%"
                max-width="90%"
                class="mx-auto"
                src="https://picsum.photos/id/11/500/300"
              ></v-img>
            </div>
            <div class="text-center">
              <span class="text-h5">
                International
              </span>
            </div>
          </v-col>
        </v-row>
      </v-container>

      <v-container>

      </v-container>

      <v-container fluid class="success px-10">
        <v-row align="center" justify="center">
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
  import SignIn from './SignIn'
  import SignUp from './SignUp'

  export default {
    components: {
      SignIn,
      SignUp,
    },
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
