<template>
  <q-layout view="lHr LpR lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          icon="menu"
          aria-label="Menu"
        />

        <q-toolbar-title>
          Visual Program
        </q-toolbar-title>
        <q-btn
          flat
          dense
          round
          @click="rightDrawerOpen = !rightDrawerOpen"
          icon="menu"
         />
      </q-toolbar>
    </q-header>-->
    <br/><br/>
    <q-page-container style="padding-top:0">
      <router-view />
    </q-page-container>
    <q-drawer
    show-if-above v-model="rightDrawerOpen"
    side="right"
    bordered>
      <previewField></previewField>
    </q-drawer>

  </q-layout>
</template>

<script>
import previewField from '../components/previewField'
export default {
  components: {
    previewField
  },
  name: 'MyLayout',

  data () {
    return {
      leftDrawerOpen: false,
      rightDrawerOpen: false
    }
  }
}
</script>
