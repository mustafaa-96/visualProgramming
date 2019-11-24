<template>
  <q-page></q-page>
  <!--<div class="q-pa-md">
    <q-layout view="hHh Lpr lff" container style="height: 300px" class="shadow-2 rounded-borders">
      <q-header elevated class="bg-black">
        <q-toolbar>
          <q-btn flat @click="drawer = !drawer" round dense icon="menu" />
          <q-toolbar-title>Visual Program</q-toolbar-title>
        </q-toolbar>
      </q-header>

      <q-drawer
        v-model="drawer"
        show-if-above
        :width="200"
        :breakpoint="500"
        bordered
        content-class="bg-grey-3"
      >
        <q-scroll-area class="fit">
          <q-btn size="25px" color="blue" no-caps>
            Filter<br>A
          </q-btn>
          <q-btn size="25px" color="blue" no-caps>
            Filter<br>B
          </q-btn> <br/>
          <q-btn size="25px" color="blue" no-caps>
            Filter<br>C
          </q-btn>
          <q-btn size="25px" color="blue" no-caps>
            Filter<br>D
          </q-btn> <br/>
        </q-scroll-area>
      </q-drawer>
    </q-layout>
  </div>-->
</template>

<script>
const menuList = [
  {
    icon: 'inbox',
    label: 'Inbox',
    separator: true
  },
  {
    icon: 'send',
    label: 'Outbox',
    separator: false
  },
  {
    icon: 'delete',
    label: 'Trash',
    separator: false
  },
  {
    icon: 'error',
    label: 'Spam',
    separator: true
  },
  {
    icon: 'settings',
    label: 'Settings',
    separator: false
  },
  {
    icon: 'feedback',
    label: 'Send Feedback',
    separator: false
  },
  {
    icon: 'help',
    iconColor: 'primary',
    label: 'Help',
    separator: false
  }
]
export default {
  data () {
    return {
      drawer: false,
      menuList
    }
  }
}
</script>
