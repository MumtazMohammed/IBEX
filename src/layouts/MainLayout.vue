<template>
  <q-layout lang="ar" dir="rtl" view="hHh lpr fff">
    <q-header reveal elevated class="bg-white" height-hint="98">
      <q-toolbar class="text-grey-7">
        <q-avatar square size="100px">
          <img src="../assets/logo.png" />
        </q-avatar>
        <q-space />
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />
      </q-toolbar>
      <!-- links tab for lg screen -->
      <q-tabs no-caps inline-label class="text-white shadow-2" align="left">
        <q-route-tab
          v-for="(menuItem, i) in menuList"
          :key="i"
          class="HeaderTab"
          :to="menuItem.route"
        >
          {{ menuItem.label }}
        </q-route-tab>
        <q-space />
        <q-route-tab icon="fa-solid fa-right-to-bracket" class="HeaderTab">
        </q-route-tab>
      </q-tabs>
    </q-header>
    <!-- open drawer links  for md and sm screen -->
    <q-drawer
      v-model="leftDrawerOpen"
      :width="300"
      :breakpoint="500"
      overlay
      elevated
      class="bg-white"
    >
      <q-scroll-area class="fit">
        <q-list>
          <template v-for="(menuItem, i) in menuList" :key="i">
            <q-item
              @click="leftDrawerOpen = !leftDrawerOpen"
              clickable
              :active="menuItem.label === 'Outbox'"
              v-ripple
            >
              <q-item-section avatar>
                <q-icon :name="menuItem.icon" />
              </q-item-section>
              <q-item-section>
                {{ menuItem.label }}
              </q-item-section>
            </q-item>
            <q-separator :key="'sep' + index" v-if="menuItem.separator" />
          </template>
        </q-list>
      </q-scroll-area>
    </q-drawer>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref } from "vue";
const menuList = [
  {
    icon: "fa-solid fa-house",
    label: "IBEX",
    route: "/page2",
    separator: true,
  },
  {
    icon: "fa-solid fa-list-check",
    label: "IBEX",
    route: "/page2",
    separator: false,
  },
  {
    icon: "fa-solid fa-hand-holding-hand",
    label: "IBEX",
    route: "/page2",
    separator: false,
  },
  {
    icon: "fa-solid fa-question",
    label: "IBEX",
    route: "/page2",
    separator: true,
  },
  {
    icon: "fa-solid fa-phone-flip",
    label: "IBEX",
    route: "/page2",
    separator: false,
  },
];
export default {
  setup() {
    const leftDrawerOpen = ref(false);
    return {
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
      drawer: ref(true),
      menuList,
    };
  },
  components: {},
};
</script>
<style lang="scss" scoped>
.q-toolbar {
  background-color: #fff;
}
.q-tabs {
  background-color: #dcaf56;
}
.HeaderTab {
  font-family: $font;
  font-size: 16px !important;
}
::v-deep i.q-icon.q-tab__icon {
  margin-left: 5px !important;
  font-size: 15px;
}
</style>
