<template>
  <q-page>
    <PuzzlePieces :color="color1" class="q-ma-md movable"
                  :style="{'left': x1 + 'px', 'top': y1 + 'px'}"
                  @mousedown.native="moveStart($event, 1)" @mouseup.native="moveEnd($event,1)" @mousemove.native="moveActive($event, 1)" ref="puzzle1"></PuzzlePieces>
    <PuzzlePieces :color="color2" class="q-ma-md movable"
                  :style="{'left': x2 + 'px', 'top': y2 + 'px'}"
                  @mousedown.native="moveStart($event, 2)" @mouseup.native="moveEnd($event,2)" @mousemove.native="moveActive($event, 2)" ref="puzzle2"></PuzzlePieces>
  </q-page>
</template>

<style>
  .movable {
    display: inline-block;
    padding: 0px;
    position: absolute;
  }
</style>

<script>
import PuzzlePieces from '../components/PuzzlePieces'
export default {
  components: {
    PuzzlePieces
  },
  data () {
    return {
      x1: 200,
      y1: 200,
      x2: 400,
      y2: 400,
      color1: 'blue',
      color2: 'blue',
      origcolor1: 'blue',
      origcolor2: 'blue'
    }
  },
  methods: {
    moveStart: function (event, index) {
      this.moving = true
      this['offsetInitX' + index] = event.offsetX
      this['offsetInitY' + index] = event.offsetY
    },
    moveActive: function (event, index) {
      if (this.moving) {
        this['x' + index] += event.offsetX - this['offsetInitX' + index]
        this['y' + index] += event.offsetY - this['offsetInitY' + index]
        var boundBox1 = this.$refs.puzzle1.$el.getBoundingClientRect()
        var boundBox2 = this.$refs.puzzle2.$el.getBoundingClientRect()
        var overlap = !(boundBox1.right < boundBox2.left ||
          boundBox1.left > boundBox2.right ||
          boundBox1.bottom < boundBox2.top ||
          boundBox1.top > boundBox2.bottom)
        if (overlap) {
          this['color' + index] = 'green'
        } else {
          this['color' + index] = this['origcolor' + index]
        }
      }
    },
    moveEnd: function (event, index) {
      this.moving = false
    }
  }
}
</script>
