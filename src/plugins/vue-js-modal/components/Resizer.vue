<template>
  <div :class="className"></div>
</template>
<script>
import { inRange } from '../utils'

export default {
  name: 'VueJsModalResizer',
  props: {
    minHeight: {
      type: Number,
      default: 0
    },
    minWidth: {
      type: Number,
      default: 0
    }
  },
  data () {
    return {
      clicked: false,
      size: {}
    }
  },
  mounted () {
    this.$el.addEventListener('mousedown', this.start, false)
  },
  computed: {
    className () {
      return { 'vue-modal-resizer': true, clicked: this.clicked }
    }
  },
  methods: {
    start (event) {
      this.clicked = true

      window.addEventListener('mousemove', this.mousemove, false)
      window.addEventListener('mouseup', this.stop, false)

      event.stopPropagation()
      event.preventDefault()
    },
    stop () {
      this.clicked = false

      window.removeEventListener('mousemove', this.mousemove, false)
      window.removeEventListener('mouseup', this.stop, false)

      this.$emit('resize-stop', {
        element: this.$el.parentElement,
        size: this.size
      })
    },
    mousemove (event) {
      this.resize(event)
    },
    resize (event) {
      var el = this.$el.parentElement

      if (el) {
        var width = event.clientX - el.offsetLeft
        var height = event.clientY - el.offsetTop

        width = inRange(this.minWidth, window.innerWidth, width)
        height = inRange(this.minHeight, window.innerHeight, height)

        this.size = { width, height }
        el.style.width = width + 'px'
        el.style.height = height + 'px'

        this.$emit('resize', {
          element: el,
          size: this.size
        })
      }
    }
  }
}
</script>
