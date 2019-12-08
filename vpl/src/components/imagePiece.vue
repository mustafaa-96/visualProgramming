<template>
  <q-img
        :src="URL"
        spinner-color="white"
        style="max-height: 500px; max-width:300px"
    />
</template>

<script>
export default {
  props: ['URL'],
  name: 'imagePiece'
}
</script>

<style>
</style>
