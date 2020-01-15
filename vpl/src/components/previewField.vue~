<template>

<q-card class="tabs">

        <q-tabs
          v-model="tab"
          dense
          class="text-grey"
          active-color="primary"
          indicator-color="primary"
          align="justify"
          narrow-indicator
        >
          <q-tab name="pic" label="Picture Preview" />
          <q-tab name="text" label="Text Preview" />
        </q-tabs>

        <q-separator />

        <q-tab-panels v-model="tab" animated>
          <q-tab-panel name="pic">
            <div class="text-h6"></div>
            There is supposed to be a picture here later.
          </q-tab-panel>

          <q-tab-panel name="text">
            <div class="text-h6"></div>
            There is supposed to be filtered text here later.
          </q-tab-panel>
        </q-tab-panels>
      </q-card>

      </template>

<script>
export default {
  name: 'previewField',
  data () {
    return {
      tab: 'pic'
    }
  }
}
</script>

<style lang="sass" scoped>
.tabs
  height: 100%

</style>
