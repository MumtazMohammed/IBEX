<template>
  <div class="q-pa-md">
    <p>Coming Soon Stay tuned</p>
    <!-- <form
      @submit.prevent.stop="onSubmit"
      @reset.prevent.stop="onReset"
      class="q-gutter-sm q-text-white"
    >
      <span class="callMe">طلب الإتصال</span>
      <span class="goel-line"></span>

      <q-input
        lang="ar"
        dark
        dir="rtl"
        ref="nameRef"
        filled
        v-model="name"
        hint="الأسم الأول واللقب "
        lazy-rules
        :rules="nameRules"
      />
      <q-input
        dir="ltr"
        dark
        ref="emailRef"
        filled
        lazy-rules
        v-model="email"
        type="email"
        hint="البريد الأكترواني "
        :rules="emailRules"
        prefix="gmail.com@"
      >
      </q-input>
      <q-input
        dir="ltr"
        ref="phoneRef"
        filled
        dark
        lazy-rules
        v-model="phone"
        mask="+966 ## ### ####"
        unmasked-value
        :rules="phoneRules"
        hint="رقم الهاتف"
      />

      <div>
        <q-btn outline label="تواصل معي" type="submit" color="primary" />
        <q-btn
          label="إعادة ضبط"
          type="reset"
          color="white"
          flat
          class="q-mr-sm text-subtitle2"
        />
      </div>
    </form> -->
  </div>
</template>

<script>
import { useQuasar } from "quasar";
import { ref } from "vue";

export default {
  name: "LetUsToContactYou",
  setup() {
    const $q = useQuasar();

    const name = ref(null);
    const nameRef = ref(null);

    const email = ref(null);
    const emailRef = ref(null);

    const phone = ref(null);
    const phoneRef = ref(null);

    const accept = ref(false);

    return {
      name,
      nameRef,
      nameRules: [(val) => (val && val.length > 0) || "قم بكاتبة إسمك  "],

      email,
      emailRef,
      emailRules: [
        (val) => (val && val.length > 0) || " قم بكتابة بريدك الأكترواني ",
      ],

      phone,
      phoneRef,
      phoneRules: [
        (val) => (val !== null && val !== "") || "إدخال رقم الهاتف",
        (val) => (val > 0 && val < 9) || "رجاً قم بإدخال رقم الهاتف صحيحاً",
      ],

      accept,

      onSubmit() {
        nameRef.value.validate();
        emailRef.value.validate();
        phoneRef.value.validate();

        if (nameRef.value.hasError || emailRef.value.hasError) {
          // form has error
        } else if (accept.value !== true) {
          $q.notify({
            color: "negative",
            message: "You need to accept the license and terms first",
          });
        } else {
          $q.notify({
            icon: "done",
            color: "positive",
            message: "Submitted",
          });
        }
      },

      onReset() {
        name.value = null;
        email.value = null;
        phone.value = null;

        nameRef.value.resetValidation();
        emailRef.value.resetValidation();
        phoneRef.value.resetValidation();
      },
    };
  },
};
</script>
<style lang="scss" scoped>
::v-deep.q-pa-md {
  border-radius: 5px;
  background-color: rgba(0, 0, 0, 0.43);
  backdrop-filter: blur(9px);
  font-family: $font;
  font-size: 13px !important;
  font-weight: 600;
  @media (min-width: 300px) {
    width: 750px !important;
  }
  @media (max-width: 300px) {
    max-width: 301.6px !important;
  }
  .callMe {
    font-size: 16px !important;
    margin: 0;
    margin-top: 5px;
    display: block;
    text-align: center;
    color: white;
  }
}
.goel-line {
  display: block;
  width: 30px;
  height: 3px;
  margin: 0 auto;
  margin: 6px auto 15px auto;
  border-radius: 50px;
  background-color: white;
}
p {
  font-size: 30px;
  font-family: sans-serif;
  color: beige;
  text-align: center;
}
</style>
