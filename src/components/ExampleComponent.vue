<template>
  <div class="col-12 landing-page mx-auto">
    <div class="div-company-tital">
      <q-avatar class="q-mb-sm" size="200px">
        <q-img
          src="../assets/logo.png"
          height="190px"
          style="max-width: 190px"
        />
      </q-avatar>
      <span class="company-tital"> IBEX </span>
      <span class="company-text"> FURNITURE </span>
      <q-space></q-space>
      <LetUsToContactYou />
    </div>
    <!-- <div class="row">
      <div class="col-4">
      </div>
    </div> -->
  </div>
</template>

<script>
import { ref } from "vue";
import LetUsToContactYou from "../components/LetUsToContactYou.vue";

export default {
  components: { LetUsToContactYou },

  setup() {
    return {};
  },
};
</script>
<style lang="scss" scoped>
::v-deep .q-img__content > div {
  flex-direction: column;
}
::v-deep.col-12.landing-page {
  height: calc(100vh - 148px);
  background-color: #0e4243;
  display: flex;
  align-items: center;
  justify-content: center;
}

::v-deep .absolute-full.text-subtitle2.flex.flex-center {
  background: #0000009d;
}
.div-company-tital {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 30px 16px;
  height: 65%;
}
.company-tital {
  font-family: sans-serif;
  font-size: 28px !important;
  letter-spacing: 6px;
  font-weight: 600;
  color: #fff;
}
.company-text {
  font-family: serif;
  font-size: 23px !important;
  display: block;
  letter-spacing: 8px;
  font-weight: 500;
  color: rgba(255, 255, 255, 0.616);
}
</style>
