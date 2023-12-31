<template>
  <modal
    name="dialog"
    height="auto"
    :classes="['v--modal', 'vue-dialog', this.params.class]"
    :width="width"
    :pivot-y="0.5"
    :adaptive="true"
    :clickToClose="dialogClickToClose"
    :transition="transition"
    @before-open="beforeOpened"
    @before-close="beforeClosed"
    @opened="$emit('opened', $event)"
    @closed="$emit('closed', $event)">
    <div class="dialog-content">
      <div v-if="params.title" class="dialog-c-title" v-html="params.title || ''"></div>
      <div v-if="params.text" class="dialog-c-text" v-html="params.text || ''"></div>
      <component v-if="params.component" v-bind="params.props" :is="params.component"></component>
    </div>
    <div
      class="vue-dialog-buttons"
      v-if="buttons">
      <button
        v-for="(button, i) in buttons"
        :class="button.class || 'vue-dialog-button'"
        type="button"
        :style="buttonStyle"
        :key="i"
        v-html="button.title"
        @click.stop="click(i, $event)">
        {{button.title}}
      </button>
    </div>
    <div v-else class="vue-dialog-buttons-none"></div>
  </modal>
</template>
<script>
export default {
  name: 'VueJsDialog',
  props: {
    width: {
      type: [Number, String],
      default: '88.88%'
    },
    clickToClose: {
      type: Boolean,
      default: true
    },
    transition: {
      type: String,
      default: 'fade'
    }
  },
  data () {
    return {
      params: {},
      defaultButtons: [{ title: 'CLOSE' }]
    }
  },
  computed: {
    buttons () {
      return this.params.buttons || this.defaultButtons
    },
    /**
      * Returns FLEX style with correct width for arbitrary number of
      * buttons.
      */
    buttonStyle () {
      return {
        flex: `1 1 ${100 / this.buttons.length}%`
      }
    },
    dialogClickToClose () {
      return this.params.clickToClose === undefined ? this.clickToClose : this.clickToClose && this.params.clickToClose
    }
  },
  methods: {
    beforeOpened (event) {
      window.addEventListener('keyup', this.onKeyUp)

      this.params = event.params || {}
      this.$emit('before-opened', event)
    },
    beforeClosed (event) {
      window.removeEventListener('keyup', this.onKeyUp)

      this.params = {}
      this.$emit('before-closed', event)
    },
    click (i, event, source = 'click') {
      const button = this.buttons[i]

      if (button && typeof button.handler === 'function') {
        button.handler(i, event, { source })
      } else {
        this.$modal.hide('dialog')
      }
    },
    onKeyUp (event) {
      if (event.which === 13 && this.buttons.length > 0) {
        const buttonIndex = this.buttons.length === 1 ? 0 : this.buttons.findIndex(button => button.default)

        if (buttonIndex !== -1) {
          this.click(buttonIndex, event, 'keypress')
        }
      }
    }
  }
}
</script>
