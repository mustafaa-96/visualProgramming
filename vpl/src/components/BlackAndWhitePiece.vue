<template>
<div :style="{'background': color}" class="puzzle">
      <span class="t"></span>
      <span class="r"></span>
      <span class="b"></span>
      <span class="l"></span>
      <span class="text">Black and White</span>
    </div>
</template>

<script>
export default {
  props: ['color'],
  name: 'PuzzlePieces',
  data () {
    return {
      bwURL: 'https://i.imgur.com/ZNWGGIY.jpg'
    }
  },
  methods: {
    addBAndW: function () {
      this.$emit('newBW', this.bwURL)
    }
  }

}
</script>

<style>

  .puzzle {
    width: 6em;
    height: 6em;
    margin: 50px;
    position: relative;
    -webkit-border-radius: .5em;
    -moz-border-radius: .5em;
    border-radius: .5em;
    cursor: pointer;
  }

  .puzzle,
  .puzzle span {
    background-color: blue;
  }
  .text {
    display: block;
    color: #fff;
    font-size: 1em;
    text-align: center;
    padding: 1.8em 0 0 1.2em;
    position: relative;
    background: transparent !important;
  }

  .puzzle .t{
    width: 2em;
    height: 2em;
    position: absolute;
    top: -1.5em;
    left: 2em;
    -webkit-border-radius: 4em;
    -moz-border-radius: 4em;
    border-radius: 4em;
  }

  .puzzle .r {
    width: 2em;
    height: 2em;
    position: absolute;
    top: 2em;
    left: 5.5em;
    -webkit-border-radius: 4em;
    -moz-border-radius: 4em;
    border-radius: 4em;
  }

  .puzzle .b {
    width: 1.8em;
    height: 1.8em;
    position: absolute;
    top: 4.5em;
    left: 2.2em;
    -webkit-border-radius: 4em;
    -moz-border-radius: 4em;
    border-radius: 4em;
    background-color: #fff;
  }

  .puzzle .l {
    width: 1.8em;
    height: 1.8em;
    position: absolute;
    top: 2.2em;
    left: -.4em;
    -webkit-border-radius: 4em;
    -moz-border-radius: 4em;
    border-radius: 4em;
    background-color: #fff;
  }
  .puzzle .button {

  }
</style>
