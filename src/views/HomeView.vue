<template>
  <div>
    <v-form class="predictionForm">
      <div class="mainLabel"><h1>Enter your movie data</h1></div>

      <v-container>
        <v-row>
          <v-col cols="12" md="6">
            <v-text-field
              dark
              outlined
              v-model="orignalTitle"
              label="original title"
              required
            ></v-text-field>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              outlined
              dark
              v-model="title"
              label="title"
              required
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12" md="6">
            <v-text-field
              dark
              outlined
              v-model="originalLanguage"
              label="original language"
              required
            ></v-text-field>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              outlined
              dark
              v-model="tagLine"
              label="tag line"
              required
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12" md="6">
            <v-text-field
              dark
              outlined
              v-model="releaseDate"
              label="Release Date"
              required
            ></v-text-field>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              outlined
              dark
              v-model="duration"
              label="Duration"
              required
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12" md="6">
            <v-text-field
              outlined
              dark
              v-model="movieBudget"
              label="movie budget"
              required
            ></v-text-field>
          </v-col>
          <v-col cols="6">
            <v-combobox
              dark
              v-model="spokenLanguages"
              label="spoken_languages"
              multiple
              outlined
            ></v-combobox>
          </v-col>
        </v-row>

        <v-row>
          <v-col cols="12">
            <v-combobox
              dark
              v-model="genres"
              label="Genras"
              multiple
              outlined
            ></v-combobox>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12" md="6">
            <v-combobox
              dark
              v-model="productionCompanies"
              label="production_companies"
              multiple
              outlined
            ></v-combobox>
          </v-col>

          <v-col cols="12" md="6">
            <v-combobox
              dark
              v-model="productionCountries"
              label="production countries"
              multiple
              outlined
            ></v-combobox>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12" md="6">
            <v-combobox
              dark
              v-model="keywords"
              label="keywords"
              multiple
              outlined
            ></v-combobox>
          </v-col>
          <v-col cols="12" md="6">
            <v-combobox
              dark
              v-model="collections"
              label="belongs to collection"
              multiple
              outlined
            ></v-combobox>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12">
            <v-textarea
              outlined
              v-model="overview"
              dark
              name="input-7-4"
              label="overview"
              value="The Woodman set to work at once, and so sharp was his axe that the tree was soon chopped nearly through."
            ></v-textarea>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12">
            <v-textarea
              outlined
              v-model="overview"
              dark
              name="input-7-4"
              label="Cast"
              value="The Woodman set to work at once, and so sharp was his axe that the tree was soon chopped nearly through."
            ></v-textarea>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12">
            <v-textarea
              outlined
              v-model="overview"
              dark
              name="input-7-4"
              label="Crew"
              value="The Woodman set to work at once, and so sharp was his axe that the tree was soon chopped nearly through."
            ></v-textarea>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="6">
            <v-checkbox
              dark
              v-model="forAdults"
              label="For Adults ?"
              color="info"
              value="1"
              hide-details
            ></v-checkbox>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12" md="12">
            <v-btn block :loading="loader" color="primary" @click="showDialog">
              predict
            </v-btn>
          </v-col>
        </v-row>

        <template>
          <div class="text-center">
            <v-dialog v-model="dialog" width="500">
              <v-card>
                <v-card-title class="text-h5 grey lighten-2">
                  Model Rating
                </v-card-title>

                <v-card-text class="text-h5 bold">
                  Your film rating is 7.9
                </v-card-text>

                <v-divider></v-divider>

                <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn color="primary" text @click="dialog = false">
                    ok
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-dialog>
          </div>
        </template>
      </v-container>
    </v-form>
  </div>
</template>

<script>
// import HelloWorld from "../components/HelloWorld";

export default {
  name: "Home-view",
  data() {
    return {
      orignalTitle: "",
      originalLanguage: "",
      title: "",
      tagLine: "",
      releaseDate: "",
      duration: "",
      movieBudget: "",
      spokenLanguages: [],
      genres: [],
      productionCompanies: [],
      productionCountries: [],
      keywords: [],
      collections: [],
      overview: "",
      forAdults: 0,
      dialog: false,
      loader: false,
    };
  },
  components: {
    // HelloWorld,
  },
  methods: {
    showDialog() {
      this.loader = true;
      setTimeout(() => {
        this.loader = false;
        this.dialog = true;
      }, 2000);
    },
  },
};
</script>

<style>
.mainLabel {
  display: flex;
  align-content: center;
  justify-content: center;
  padding: 10px;
  color: antiquewhite;
}

.predictionForm {
  padding: 20px;
  background-color: rgb(43, 42, 51);
}
</style>
