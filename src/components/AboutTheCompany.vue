<template>
  <q-layout class="bg-grey-1">
    <q-page-container>
      <q-page padding>
        <!-- <div class="relative-position">
          <div class="text-center text-grey-3 AboutUsTital"></div>
          <span class="AboutUsTital-line"></span>
        </div> -->

        <q-carousel
          v-model="slide"
          transition-prev="scale"
          transition-next="scale"
          swipeable
          animated
          vertical
          control-color="blue"
          padding
          show-
          height="300px"
          class="bg-grey-2 text-grey shadow-1 rounded-borders"
        >
          <q-carousel-slide name="style" class="row">
            <div class="col-4 AboutUsTital">
              <div class="Avatar-tital">
                <q-avatar square size="170px">
                  <img src="../assets/goal.png" />
                </q-avatar>
              </div>
            </div>
            <div class="col-8 AboutUsTital">
              <div class="text-center">
                <span class="goel-tital"> أهــدافــنـا</span>

                <div>
                  <span class="goel-text-1 text-grey-6">
                    - تطوير الوحدات السكنية فى ما يتماشي مع طلب العملاء بأحسن
                    المواصفات.
                  </span>
                  <span class="goel-text text-grey-6">
                    - توفير الوحدات السكنية لكل من المستثمر والمالك بجودة الكود
                    السعودي.
                  </span>
                </div>
              </div>
            </div>
          </q-carousel-slide>
          <q-carousel-slide name="layers" class="row">
            <div class="col-4 AboutUsTital">
              <div class="Avatar-tital">
                <q-avatar square size="170px">
                  <img src="../assets/visionary.png" />
                </q-avatar>
              </div>
            </div>
            <div class="col-8 AboutUsTital">
              <div class="text-center">
                <div>
                  <span class="goel-tital">رؤيــتــنـا</span>
                  <span class="goel-text text-grey-6">
                    نهضة عمرانية لتطوير آلية العمل بالمواقع تحت إشراف هندسي
                    ومقاييس عالمية
                  </span>
                </div>
              </div>
            </div>
          </q-carousel-slide>
          <q-carousel-slide name="map" class="row">
            <div class="col-4 AboutUsTital">
              <div class="Avatar-tital">
                <q-avatar square size="170px">
                  <img src="../assets/value.png" />
                </q-avatar>
              </div>
            </div>
            <div class="col-8 AboutUsTital">
              <div class="text-center">
                <div>
                  <span class="goel-tital">قــيــمــنـا</span>
                  <span class="goel-text text-grey-6">
                    المصداقية بالتعامل مع العميل فيما يخص البناء والبيع والشراء.
                    <br />
                    الضمان على كل الوحدات السكنية فى مشاريعنا وتطبيق معايير
                    الجودة والسلامة
                  </span>
                </div>
              </div>
            </div>
          </q-carousel-slide>
        </q-carousel>
        <div class="row q-mt-sm justify-center">
          <q-btn-toggle
            glossy
            v-model="slide"
            :options="[
              { label: 1, value: 'style' },
              { label: 2, value: 'layers' },
              { label: 3, value: 'map' },
            ]"
          />
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
      slide: ref("style"),
      lorem:
        "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Itaque voluptatem totam, architecto cupiditate officia rerum, error dignissimos praesentium libero ab nemo.",
    };
  },
};
</script>
<style lang="scss" scoped>
::v-deep.q-layout.q-layout--standard.bg-grey-1 {
  min-height: auto !important;
}
::v-deep
  .q-carousel.q-panel-parent.q-carousel--with-padding.q-carousel--arrows-vertical.bg-grey-2.text-grey.shadow-1.rounded-borders {
  min-width: 800px;
  margin: 0 auto;
  @media (max-width: 1000px) {
    min-width: auto;
  }
}
::v-deep main.q-page.q-layout-padding {
  min-height: 400px !important;
  margin: auto 0;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
::v-deep .q-panel-parent {
  overflow: visible;
}

.AboutUsTital {
  font-family: $font;
  font-size: 22px;
  font-weight: 600;
  margin-bottom: 7px;
  position: relative;
  z-index: 1;
  margin: auto;
}
.goel-tital {
  font-family: $font;
  font-size: 23.7px;
  font-weight: 500;
  display: block;
  margin: 0 auto;
  margin-bottom: 5px;
  color: rgba(67, 67, 67, 0.899);
  position: relative;
  z-index: 4;
}

.goel-text-1 {
  font-family: $font;
  font-size: 20px;
  font-weight: 500;
  display: block;
  line-height: 1.5;
  position: relative;
  z-index: 4;
  padding: 7px;
}
.goel-text {
  font-family: $font;
  font-size: 20px;
  font-weight: 500;
  display: block;
  line-height: 1.5;
  position: relative;
  z-index: 4;
  padding: 7px;
}
.goel-text::after {
  content: "";
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  background-color: $primary;
  width: 20%;
  height: 5px;
  color: white;
  z-index: -1;
  border-radius: 50px;
}
.goel-text::before {
  content: "";
  position: absolute;
  bottom: -15px;
  left: 50%;
  transform: translateX(-50%);
  background-color: white;
  width: 15px;
  height: 15px;
  color: white;
  z-index: 0;
  border-radius: 50%;
  box-shadow: 0px 0px 0px 3px #1976d2;
}
.Avatar-tital {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
::v-deep.q-btn-group > .q-btn-item {
  border-radius: 0px;
}

::v-deep .q-btn-group.row.no-wrap.q-btn-group--glossy.inline.q-btn-toggle {
  overflow: hidden;
}
</style>
