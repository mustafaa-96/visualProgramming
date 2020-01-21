<template>
  <q-layout view="lHr LpR lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title>
          Visual Program
        </q-toolbar-title>
      </q-toolbar>
    </q-header>-->
    <br/><br/>
    <q-page-container style="padding-top:0">
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script>
export default {
  components: {
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
