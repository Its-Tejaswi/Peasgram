<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-white text-grey-10 constrain" bordered>
      <q-toolbar class="constrain">
        <q-btn
          class="large-screen-only q-mr-sm"
          to="/camera"
          flat
          round
          color="grey-10"
          size="15px"
          dense
          icon="eva-camera-outline"
        />
        <q-separator class="large-screen-only" spaced vertical />
        <q-toolbar-title class="q-grand-hotel text-weight-bold">
          Quasagram
        </q-toolbar-title>
        <q-btn
          class="large-screen-only"
          to="/"
          flat
          round
          color="grey-10"
          size="15px"
          dense
          icon="eva-home-outline"
        />
      </q-toolbar>
    </q-header>
    <q-footer class="bg-white small-screen-only" bordered>
      <q-tabs
        active-color="primary"
        class="text-grey-10"
        indicator-color="transparent"
      >
        <q-route-tab to="/" icon="eva-home-outline" />
        <q-route-tab to="/camera" icon="eva-camera-outline" />
      </q-tabs>
    </q-footer>

    <q-page-container class="bg-grey-2">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: "MainLayout",
  data() {
    return {};
  },
};
</script>

<style lang="sass">
.q-toolbar
    height: 60px
.q-toolbar__title
    font-size: 39px
    @media (max-width: $breakpoint-xs-max)
        text-align: center
.q-footer
    .q-tab__icon
        font-size: 30px
</style>
