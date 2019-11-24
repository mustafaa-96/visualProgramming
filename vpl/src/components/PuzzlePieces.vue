<template>
  <div :style="{'background': color}" class="pointer"></div>
</template>

<script>
export default {
  props: ['color'],
  name: 'PuzzlePieces'
}
</script>

<style>
  .pointer {
    width: 75px;
    height: 40px;
    position: relative;
  }
  .pointer:after {
    content: "";
    position: absolute;
    left: 0;
    bottom: 0;
    width: 0;
    height: 0;
    border-left: 20px solid white;
    border-top: 20px solid transparent;
    border-bottom: 20px solid transparent;
  }
  .pointer:before {
    content: "";
    position: absolute;
    right: -20px;
    bottom: 0;
    width: 0;
    height: 0;
    border-left: 20px solid orange;
    border-top: 20px solid transparent;
    border-bottom: 20px solid transparent;
  }
</style>
