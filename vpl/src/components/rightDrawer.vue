  <template>
    <q-drawer
    show-if-above v-model="rightDrawerOpen"
    side="right"
    bordered>
      <q-card class="tabs">

        <q-tabs
          v-model="tab"
          dense
          class="text-white bg-orange"
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
            <imagePiece
            :URL=previewURL
            :contrast=previewContrast
            >
            </imagePiece>
          </q-tab-panel>

          <q-tab-panel name="text"
          class="bg-blue">
            <div class="text-h6"></div>
            {{previewText}}
          </q-tab-panel>
        </q-tab-panels>
      </q-card>
    </q-drawer>
    </template>

<script>
import imagePiece from '../components/imagePiece'
export default {
  components: {
    imagePiece
  },
  name: 'previewField',
  props: ['previewURL', 'previewContrast', 'previewText'],
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
