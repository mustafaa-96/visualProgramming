<template>
<q-drawer
      show-if-above v-model="open"
      side="left"
      bordered
      content-class="bg-grey-2"
    >
      <q-scroll-area class="fit">
    <div class="a">Filter Menu</div>
    <br/> <br/>
    <q-btn-dropdown class="dropdown" color="orange" label="Select Analysis Procedure">
      <q-list>
        <q-item class="item" clickable v-close-popup @click="onItemClick1">
          <q-item-section>
            <q-item-label>Image Processing</q-item-label>
          </q-item-section>
        </q-item>

        <q-item class="item" clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>Page Layout</q-item-label>
          </q-item-section>
        </q-item>

        <q-item class="item" clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>Image Segmentation</q-item-label>
          </q-item-section>
        </q-item>

        <q-item class="item" clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>OCR</q-item-label>
          </q-item-section>
        </q-item>

        <q-item class="item" clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>Comparison</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-btn-dropdown> <br/> <br/> <br/>
    <q-btn size="25px" color="orange" no-caps @click="addBAndW()">
      Black<br>and White
    </q-btn> <div class="space"/>
    <q-btn size="20px" color="orange" no-caps @click="contrastSliderOpen = !contrastSliderOpen">
      Change<br>Contrast
    </q-btn> <div class="space"/> <br/> <br/> <br/>
    <q-btn size="25px" color="orange" no-caps @click="filterText()">
      Filter text
    </q-btn> <div class="space"/>
    <q-btn size="25px" color="orange" no-caps>
      Filter<br>D
    </q-btn> <br/>
    <q-form v-model="contrastSliderOpen" class="q-pa-md">
      <q-slider
        v-model="value"
        @input="updateContrast"
        :min="0"
        :max="200"
        :step="4"
        label="contrastSlider"
        color="orange"
        />
    </q-form>
  </q-scroll-area>
    </q-drawer>
</template>
<style>
  .fit{
    background: #027BE3;
  }
  .space{
    width:35px;
    height:auto;
    display:inline-block;
  }
  div.a {
    font-size: 33.5px;
    font-style: normal;
    text-align: center;
    background: orange;
    color: white;
  }
  .item{
    text-align: center;
    background: black;
    color: white;
  }
  .dropdown{
    width: 100%;
  }
</style>

<script>
export default {
  name: 'FilterMenu',
  methods: {
    onItemClick () {
      // TODO: show button group for each analysis procedure
    },
    onItemClick1 () {
      // TODO: show button group for each analysis procedure
    },
    changeState: function () {
      this.open = !this.open
    },
    addBAndW: function () {
      this.$emit('newBW')
    },
    updateContrast: function () {
      this.$emit('contrast', this.value)
    },
    filterText: function () {
      this.$emit('text')
    }
  },
  data () {
    return {
      open: false,
      contrastSliderOpen: false,
      value: 100,
      bwURL: 'https://i.imgur.com/ZNWGGIY.jpg'
    }
  },
  props: {
    leftDrawerOpen: Boolean
  }
}
</script>

<style scoped>

</style>
