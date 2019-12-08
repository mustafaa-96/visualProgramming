<template>
  <q-img
        :src="URL"
        spinner-color="white"
        :style="{'width':'200px', 'filter': 'contrast('+ contrast + '%)'}"
    />
</template>

<script>
import NewFilterMenu from '../components/NewFilterMenu'
export default {
  props: ['URL', 'contrast'],
  name: 'imagePiece',
  data () {
    return {
      value: NewFilterMenu.value
    }
  }
}

</script>

<style>
</style>
