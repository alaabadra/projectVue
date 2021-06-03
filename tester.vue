<template>
  <div class="container-fluid">
    <div class="row">
      <v-navigation-drawer absolute permanent right class="p-2" width="30vw">
        <v-select class="w-100" label="البيان" clearable></v-select>
        <v-select class="w-100" label="الإشعار" clearable></v-select>
        <v-menu
          v-model="menu2"
          :close-on-content-click="false"
          :nudge-left="40"
          transition="scale-transition"
          offset-y
          min-width="auto"
        >
          <template v-slot:activator="{ on, attrs }">
            <v-text-field
              v-model="dates"
              label="تاريخ مخصص"
              prepend-inner-icon="mdi-calendar"
              readonly
              v-bind="attrs"
              v-on="on"
            ></v-text-field>
          </template>
          <v-date-picker v-model="dates" range></v-date-picker>
        </v-menu>
        <div class="d-flex">
          <div style="width: 45% !important" class="d-flex">
            <label
              style="background-color:white; width: 20%"
              class="p-0 h-100 mt-2"
              >من</label
            >
            <v-chip
              class="ma-2 ml-auto p-0"
              style="width: 80% !important;"
              label
              color="grey lighten-3"
            >
              {{ dates[0] }}
            </v-chip>
          </div>
          <div style="width: 45% !important" class="d-flex mr-auto">
            <label
              style="background-color:white; width: 20%"
              class="p-0 h-100 mt-2"
              >إلي</label
            >
            <v-chip
              class="ma-2 ml-auto p-0 text-center"
              style="width: 80% !important"
              label
              color="grey lighten-3"
            >
              {{ dates[1] }}
            </v-chip>
          </div>
        </div>
        <v-card elevation="3" class="mt-10 p-1" color="grey lighten-3">
          <v-card-text class="row p-0 mx-auto">
            <div
              class="ma-2 rounded-lg custom-shadow-green mx-auto p-0 d-flex white"
              label
              style="width: 32%;
              height: 2rem;
              max-height: 2rem !important"
            >
              <v-chip
                style="width: 100% !important"
                class="ml-auto p-0 rounded-lg"
              >
                <div class="hinter-green p-0 ml-auto ">
                  <p class="mt-10 mr-3 text-center mx-auto white--text">دولار</p>
                </div>
              </v-chip>
              <v-checkbox dense class="mt-0" color="green"></v-checkbox>
            </div>
            <div
              class="ma-2 rounded-lg custom-shadow mx-auto p-0 d-flex white"
              label
              style="width: 32%;
              height: 2rem;
              max-height: 2rem !important"
            >
              <v-chip
                style="width: 100% !important"
                class="ml-auto p-0 rounded-lg"
              >
                <div class="hinter-white p-0 ml-auto ">
                  <p class="mt-10 mr-3 text-center mx-auto black--text">تركية</p>
                </div>
              </v-chip>
              <v-checkbox dense class="mt-0" color="grey"></v-checkbox>
            </div>
            <div
              class="ma-2 rounded-lg custom-shadow-blue mx-auto p-0 d-flex white"
              label
              style="width: 32%;
              height: 2rem;
              max-height: 2rem !important"
            >
              <v-chip
                style="width: 100% !important"
                class="ml-auto p-0 rounded-lg"
              >
                <div class="hinter-blue p-0 ml-auto ">
                  <p class="mt-10 mr-3 text-center mx-auto white--text">يورو</p>
                </div>
              </v-chip>
              <v-checkbox dense class="mt-0" color="blue"></v-checkbox>
            </div>
            <div
              class="ma-2 rounded-lg custom-shadow mx-auto p-0 d-flex white"
              label
              style="width: 32%;
              height: 2rem;
              max-height: 2rem !important"
            >
              <v-chip
                style="width: 100% !important"
                class="ml-auto p-0 rounded-lg"
              >
                <div class="hinter-white p-0 ml-auto ">
                  <p class="mt-10 mr-3 text-center mx-auto black--text">سوري</p>
                </div>
              </v-chip>
              <v-checkbox dense class="mt-0" color="grey"></v-checkbox>
            </div>
            <div
              class="ma-2 rounded-lg custom-shadow-red mx-auto p-0 d-flex white"
              label
              style="width: 32%;
              height: 2rem;
              max-height: 2rem !important"
            >
              <v-chip
                style="width: 100% !important"
                class="ml-auto p-0 rounded-lg"
              >
                <div class="hinter-red p-0 ml-auto ">
                  <p class="mt-10 mr-3 text-center mx-auto white--text">مصري</p>
                </div>
              </v-chip>
              <v-checkbox dense class="mt-0" color="red"></v-checkbox>
            </div>
            <div
              class="ma-2 rounded-lg custom-shadow mx-auto p-0 d-flex white"
              label
              style="width: 32%;
              height: 2rem;
              max-height: 2rem !important"
            >
              <v-chip
                style="width: 100% !important"
                class="ml-auto p-0 rounded-lg"
              >
                <div class="hinter-white p-0 ml-auto ">
                  <p class="mt-10 mr-3 text-center mx-auto black--text">استرليني</p>
                </div>
              </v-chip>
              <v-checkbox dense class="mt-0" color="grey"></v-checkbox>
            </div>
          </v-card-text>
        </v-card>
        <div class="row w-100 mt-5 mx-auto">
          <div class="w-100">
            <v-checkbox
              color="green"
              label="فعال"
              dense
              flat
              style="width: 32%; "
              class="mx-auto shadow-sm rounded-lg custom-shadowbg-white"
            >
              <template v-slot:message>
                <span>hhhhh</span>
              </template>
              <template v-slot:label>
                <span style="font-size: .7rem; width: 100%;" class="text-right"
                  >غير فعال</span
                >
              </template>
            </v-checkbox>
          </div>

          <div style="width: 47%;" class="mx-auto mt-3 text-right">
            <label
              for=""
              style="width: 100%; font-size: .8rem"
              class="text-right"
              >إسم المرسل المدين</label
            >
            <b-input
              type="text"
              style="width: 100%; height: 1.5rem"
              class="mx-auto custom-shadowborder"
            />
          </div>
          <div style="width: 47%;" class="mx-auto mt-3 text-right">
            <label
              for=""
              style="width: 100%; font-size: .8rem"
              class="text-right"
              >إسم المرسل المدين</label
            >
            <b-input
              type="text"
              style="width: 100%; height: 1.5rem"
              class="mx-auto custom-shadowborder"
            />
          </div>
        </div>
      </v-navigation-drawer>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      dates: [],
      menu: false,
    };
  },
  mounted() {},
};
</script>
<style scoped>
.hinter-blue {
  width: 100px !important;
  height: 2rem;
  border-bottom: solid 100px #0093f7;
  border-left: solid 15px white;
  background-color: coral;
  vertical-align: center;
  text-align: center center;
}
.hinter-white {
  width: 100px !important;
  height: 2rem;
  border-bottom: solid 100px #EEEEEE;
  border-left: solid 15px white;
  background-color: coral;
  vertical-align: center;
  text-align: center center;
}
.hinter-green {
  width: 120px !important;
  height: 2rem;
  border-bottom: solid 100px #4caf50;
  border-left: solid 15px white;
  background-color: white;
  vertical-align: center;
  text-align: center center;
}
/* .hinter-green::before {
  content: "hello";
} */
.hinter-red {
  width: 120px !important;
  height: 2rem;
  border-bottom: solid 100px red;
  border-left: solid 15px white;
  background-color: coral;
  vertical-align: center;
  text-align: center center;
}
.v-messages__message {
  display: none !important;
}
div .v-messages .theme--light {
  display: none !important;
}
.custom-shadow {
  box-shadow: 2px 2px 3px grey;
}
.custom-shadow-green {
  box-shadow: 2px 2px 15px #A5D6A7;
}
.custom-shadow-blue {
  box-shadow: 2px 2px 15px #90CAF9;
}
.custom-shadow-red {
  box-shadow: 2px 2px 15px#E57373;
}
/* .v-input input{
  height: 12px !important;
  width: 12px !important;
} */
#styled-input {
  height: 10px !important;
  font-size: 20pt !important;
}
.styled-input label[for] {
  height: 10px !important;
  font-size: 20pt !important;
}
</style>
