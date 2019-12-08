<template>
  <q-scroll-area class="fit">
    <div class="a">Filter Menu</div>
    <br/> <br/>
    <q-btn-dropdown class="dropdown" color="orange" label="Select Analysis Procedure">
      <q-list>
        <q-item class="item" clickable v-close-popup @click="onItemClick">
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
    <q-btn size="25px" color="orange" no-caps @click="addBWFilter">
      Black<br>and White
    </q-btn> <div class="space"/>
    <q-btn size="25px" color="orange" no-caps>
      Filter<br>B
    </q-btn> <br/> <br/> <br/>
    <q-btn size="25px" color="orange" no-caps>
      Filter<br>C
    </q-btn> <div class="space"/>
    <q-btn size="25px" color="orange" no-caps>
      Filter<br>D
    </q-btn> <br/>
  </q-scroll-area>
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
  data () {
    return {
      text: 'green'
    }
  },
  methods: {
    onItemClick () {
      // TODO: show button group for each analysis procedure
    },
    addBWFilter: function () {
      this.$emit('emmited', this.text)
    }
  }
}
</script>

<style scoped>

</style>
