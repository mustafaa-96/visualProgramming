<template>
  <q-page>
    <menuBar @emitted="receiveData"></menuBar>
    <PuzzlePieces :color="color1" class="q-ma-md movable"
                  :style="{'left': x1 + 'px', 'top': y1 + 'px'}"
                  @mousedown.native="moveStart($event, 1)" @mouseup.native="moveEnd($event,1)" @mousemove.native="moveActive($event, 1)" ref="puzzle1"></PuzzlePieces>
    <BlackAndWhitePiece :color="color1" class="q-ma-md movable"
                  :style="{'left': x2 + 'px', 'top': y2 + 'px'}"
                  @mousedown.native="moveStart($event, 2)" @mouseup.native="moveEnd($event,2)" @mousemove.native="moveActive($event, 2)" ref="puzzle2"></BlackAndWhitePiece>
    <NewFilterMenu @contrast="getContrast" @newBW="setBWCoord" @text="setText"></NewFilterMenu>
    <rightDrawer :previewURL="sourceURL"
                 :previewContrast="contrast"
                 :previewText="text">
                 </rightDrawer>
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
import NewFilterMenu from '../components/NewFilterMenu'
import menuBar from '../components/menuBar'
import PuzzlePieces from '../components/PuzzlePieces'
import BlackAndWhitePiece from '../components/BlackAndWhitePiece'
import rightDrawer from '../components/rightDrawer'
export default {
  components: {
    PuzzlePieces,
    menuBar,
    NewFilterMenu,
    BlackAndWhitePiece,
    rightDrawer
  },
  data () {
    return {
      // Puzzle1
      x1: 1000,
      y1: 1000,
      // Puzzle2
      x2: 1000,
      y2: 1000,
      // BlackAndWhite
      x4: 1000,
      y4: 1000,
      color1: '',
      color2: 'blue',
      origcolor1: 'yellow',
      origcolor2: 'blue',
      sourceURL: '',
      text: '',
      contrast: 100
    }
  },
  methods: {
    newBWFilter: function (f) {
      this.sourceURL = f
    },
    receiveData: function (e) {
      this.sourceURL = e
      this.x1 = 100
      this.y1 = 100
    },
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
        var overlap = !(boundBox1.right + 5 < boundBox2.left ||
          boundBox1.left - 5 > boundBox2.right ||
          boundBox1.bottom + 5 < boundBox2.top ||
          boundBox1.top - 5 > boundBox2.bottom)
        if (overlap) {
          this.sourceURL = 'https://i.imgur.com/ZNWGGIY.jpg'
        } else {
          this.sourceURL = 'https://upload.wikimedia.org/wikipedia/commons/thumb/8/80/Houghton_MS_Gr_20_-_Theogeny%2C_10.jpg/1200px-Houghton_MS_Gr_20_-_Theogeny%2C_10.jpg'
        }
      }
    },
    moveEnd: function (event, index) {
      this.moving = false
    },
    getContrast: function (event) {
      this.contrast = event
    },
    setBWCoord: function () {
      this.x2 = 200
      this.y2 = 400
    },
    setText: function () {
      if (this.sourceURL !== '' && this.contrast === 100) {
        this.text = 'Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet'
      } else if (this.contrast !== 100) {
        alert('Change contrast back to default value (100)')
        this.text = ''
      } else if (this.sourceURL === 'https://upload.wikimedia.org/wikipedia/commons/thumb/8/80/Houghton_MS_Gr_20_-_Theogeny%2C_10.jpg/1200px-Houghton_MS_Gr_20_-_Theogeny%2C_10.jpg') {
        alert('Remove Black and White Filter')
        this.text = ''
      } else if (this.contrast !== 100 && this.sourceURL === 'https://upload.wikimedia.org/wikipedia/commons/thumb/8/80/Houghton_MS_Gr_20_-_Theogeny%2C_10.jpg/1200px-Houghton_MS_Gr_20_-_Theogeny%2C_10.jpg') {
        alert('Remove Black and White Filter and change contrast back to default value (100)')
        this.text = ''
      }
    }
  }
}
</script>
