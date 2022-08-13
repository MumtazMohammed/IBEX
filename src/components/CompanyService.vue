<template>
  <q-layout>
    <q-page-container>
      <q-page padding>
        <span class="Service-tital">خــدمــاتــنـا</span>
        <div class="q-pa-md row justify-center items-start">
          <div class="col-3 q-ma-sm">
            <q-card
              class="my-card"
              flat
              @mouseover="expanded = true"
              @mouseleave="expanded = false"
            >
              <q-img src="https://cdn.quasar.dev/img/parallax2.jpg">
                <div class="absolute-bottom text-center">
                  <div class="card-tital">
                    وسطاء فرديين

                    <q-icon
                      color="white"
                      :name="
                        expanded ? 'keyboard_arrow_up' : 'keyboard_arrow_down'
                      "
                    />
                  </div>
                </div>
              </q-img>
              <q-slide-transition>
                <div v-show="expanded" class="bg-primary Drop-Info">
                  <q-card-section class="bg-grey-2">
                    <div class="text-caption text-grey-8">
                      نبذة عن الخدمة نبذة عن الخدمة نبذة عن الخدمة نبذة عن
                      الخدمة نبذة عن الخدمة
                    </div>
                  </q-card-section>
                  <q-card-actions class="justify-center">
                    <q-btn
                      padding="3px 30px"
                      color="grey-2"
                      class="text-grey-8"
                      label="رؤية المزيد"
                    />
                  </q-card-actions>
                </div>
              </q-slide-transition>
            </q-card>
          </div>
          <div class="col-3 q-ma-sm">
            <q-card
              class="my-card"
              flat
              @mouseover="expanded2 = true"
              @mouseleave="expanded2 = false"
            >
              <q-img src="https://cdn.quasar.dev/img/parallax2.jpg">
                <div class="absolute-bottom text-center">
                  <div class="card-tital">
                    مــشـاريــع

                    <q-icon
                      color="white"
                      :name="
                        expanded2 ? 'keyboard_arrow_up' : 'keyboard_arrow_down'
                      "
                    />
                  </div>
                </div>
              </q-img>
              <q-slide-transition>
                <div v-show="expanded2" class="bg-primary Drop-Info">
                  <q-card-section class="bg-grey-2">
                    <div class="text-caption text-grey-8">
                      نبذة عن الخدمة نبذة عن الخدمة نبذة عن الخدمة نبذة عن
                      الخدمة نبذة عن الخدمة
                    </div>
                  </q-card-section>
                  <q-card-actions class="justify-center">
                    <q-btn
                      padding="3px 30px"
                      color="grey-2"
                      class="text-grey-8"
                      label="رؤية المزيد"
                    />
                  </q-card-actions>
                </div>
              </q-slide-transition>
            </q-card>
          </div>
          <div class="col-3 q-ma-sm">
            <q-card
              class="my-card"
              flat
              @mouseover="expanded3 = true"
              @mouseleave="expanded3 = false"
            >
              <q-img src="https://cdn.quasar.dev/img/parallax2.jpg">
                <div class="absolute-bottom text-center">
                  <div class="card-tital">
                    وحــدات مــتـاحــة
                    <q-icon
                      color="white"
                      :name="
                        expanded3 ? 'keyboard_arrow_up' : 'keyboard_arrow_down'
                      "
                    />
                  </div>
                </div>
              </q-img>
              <q-slide-transition>
                <div v-show="expanded3" class="bg-primary Drop-Info">
                  <q-card-section class="bg-grey-2">
                    <div class="text-caption text-grey-8">
                      نبذة عن الخدمة نبذة عن الخدمة نبذة عن الخدمة نبذة عن
                      الخدمة نبذة عن الخدمة
                    </div>
                  </q-card-section>
                  <q-card-actions class="justify-center">
                    <q-btn
                      padding="3px 30px"
                      color="grey-2"
                      class="text-grey-8"
                      label="رؤية المزيد"
                    />
                  </q-card-actions>
                </div>
              </q-slide-transition>
            </q-card>
          </div>
        </div>
      </q-page>
    </q-page-container>
  </q-layout>
</template>
<script>
import { ref } from "vue";

export default {
  setup() {
    return {
      expanded: ref(false),
      expanded2: ref(false),
      expanded3: ref(false),
      lorem:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
    };
  },
};
</script>
<style lang="scss" scoped>
::v-deep.q-layout.q-layout--standard {
  min-height: 470px !important;
}
::v-deep main.q-page {
  min-height: 470px !important;
}
::v-deep .absolute-bottom.text-center {
  padding: 5px;
}
::v-deep i.q-icon.text-white.notranslate.material-icons {
  float: left;
}

.my-card {
  width: 100%;
  max-width: 350px;
  overflow: hidden;
}
.card-tital {
  font-family: $font;
  font-size: 18.7px;
  font-weight: 500;
  display: block;
  text-align: center;
  color: rgb(255, 255, 255);
  position: relative;
  z-index: 4;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.Service-tital {
  font-family: $font;
  font-size: 23.7px;
  font-weight: 500;
  display: block;
  margin-bottom: 5px;
  text-align: center;
  color: rgba(67, 67, 67, 0.899);
  position: relative;
  z-index: 4;
}
.Service-tital::after {
  content: "";
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  background-color: $primary;
  width: 2%;
  height: 4px;
  color: white;
  z-index: -1;
  border-radius: 50px;
}
.Drop-Info {
  font-family: $font;
}
</style>
