<template lang="pug">
q-dialog(:value='value' maximized @input='$emit("input", $event)')
  q-card.full-height.flex.column
    q-card-section(style='flex: 0 0 auto')
      .text-h6
        i.fas.fa-folder-open
        span.q-ml-md Load Block
    q-card-section
      DiffblocksTable(:diffblocks='diffblocks')
    q-card-actions(style='flex: 0 0 auto')
      q-btn.full-width(color='negative' @click='$emit("input", $event.target.value)') Cancel
</template>

<script>
import DiffblocksTable from '../library/DiffblocksTable'
import store from 'store'
import {mapState} from 'vuex'

/**
 * Displays a dialog box for grabbing a Block
 */
export default {
  name: 'DialogLoadBlock',

  props: ['value', 'type'],

  components: {DiffblocksTable},

  computed: {
    ...mapState(['diffblocks'])
  },
}
</script>