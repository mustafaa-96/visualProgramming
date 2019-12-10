<template>
  <q-img
        :src="URL"
        spinner-color="white"
        style="max-height: 500px; max-width: 300px; filter: contrast(200)"
    />
</template>

<style>
</style>

<script>
import FilterMenu from './FilterMenu'
export default {
  props: ['URL'],
  name: 'imagePiece',
  data () {
    return {
      value: FilterMenu.value
    }
  }
}
</script>
