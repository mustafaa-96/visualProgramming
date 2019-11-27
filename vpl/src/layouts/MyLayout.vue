<template>
  <q-layout view="lHr LpR lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="left = !left"
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
          @click="right = !right"
          icon="menu"
         />
        <!--<div>Quasar v{{ $q.version }}</div>-->
      </q-toolbar>
    </q-header>-->

    <q-drawer
      show-if-above v-model="left"
      side="left"
      bordered
      content-class="bg-grey-2"
    >
      <FilterMenu></FilterMenu>
      <!--<q-list>
        <q-item-label header>Essential Links</q-item-label>
        <q-item clickable tag="a" target="_blank" href="https://quasar.dev">
          <q-item-section avatar>
            <q-icon name="school" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Docs</q-item-label>
            <q-item-label caption>quasar.dev</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="a" target="_blank" href="https://github.quasar.dev">
          <q-item-section avatar>
            <q-icon name="code" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Github</q-item-label>
            <q-item-label caption>github.com/quasarframework</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="a" target="_blank" href="https://chat.quasar.dev">
          <q-item-section avatar>
            <q-icon name="chat" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Discord Chat Channel</q-item-label>
            <q-item-label caption>chat.quasar.dev</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="a" target="_blank" href="https://forum.quasar.dev">
          <q-item-section avatar>
            <q-icon name="record_voice_over" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Forum</q-item-label>
            <q-item-label caption>forum.quasar.dev</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="a" target="_blank" href="https://twitter.quasar.dev">
          <q-item-section avatar>
            <q-icon name="rss_feed" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Twitter</q-item-label>
            <q-item-label caption>@quasarframework</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="a" target="_blank" href="https://facebook.quasar.dev">
          <q-item-section avatar>
            <q-icon name="public" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Facebook</q-item-label>
            <q-item-label caption>@QuasarFramework</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>-->
    </q-drawer><br/><br/>
    <menuBar></menuBar>

    <q-page-container>
      <router-view />
    </q-page-container>
    <q-drawer
    show-if-above v-model="right"
    side="right"
    bordered>
      <previewField></previewField>
    </q-drawer>

  </q-layout>
</template>

<script>
import FilterMenu from '../components/FilterMenu'
import menuBar from '../components/menuBar'
import previewField from '../components/previewField'
export default {
  components: {
    FilterMenu,
    menuBar,
    previewField
  },
  name: 'MyLayout',

  data () {
    return {
      left: false,
      right: false
    }
  }
}
</script>
