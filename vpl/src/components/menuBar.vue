<template>
  <div class="head">
    <div class="menuBar">
      <q-btn class="menuButton" round color="white" text-color="black" icon="folder_open" @click="open()"/>
      <q-btn class="menuButton" round color="white" text-color="black" icon="save" @click="save()"/>
      <q-btn class="menuButton" round color="white" text-color="black" icon="rotate_left" @click="undo()"/>
      <q-btn class="menuButton" round color="white" text-color="black" icon="rotate_right" @click="redo()"/>
      <q-btn class="menuButton" round color="white" text-color="black" icon="settings_applications" @click="openConfig()"/>
      <q-btn class="menuButton" round color="white" text-color="black" icon="contact_support" @click="openHelp()"/>
    </div>
  </div>
</template>

<script>
export default {
  // name: 'ComponentName',
  data () {
    return {
    }
  },
  methods: {
    open: function () {
      alert('Under construction')
    },
    save: function () {
      alert('Under construction')
    },
    undo: function () {
      alert('Under construction')
    },
    redo: function () {
      alert('Under construction')
    },
    openConfig: function () {
      alert('Under construction')
    },
    openHelp: function () {
      alert('Under construction')
    }
  }
}
</script>

<style>
  .head{
    position: absolute;
    padding-top: 5px;
    height:85px;
    width:100%;
    border-style: none none solid none;
    border-width:1px;
    border-color: gray;
  }
  .menuBar{
    position: relative;
    margin: auto;
    height: 75px;
    width: 610px; /*width=610px, because there are 5px borders on each side making the "usable width" 600px*/
    border-style: solid;
    border-width: 5px;
    border-radius:15px;
    border-color: gray;
  }
  .menuButton{
    position:relative;
    height: 60px;
    width: 60px;
    margin-left: 20px;
    margin-right: 20px;
  }
</style>
