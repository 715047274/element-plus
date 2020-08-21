<template>
  <div>
    <el-popper>
      <slot name="content">
        {{ content }}
      </slot>
    </el-popper>
  </div>
</template>
<script lang='ts'>
import { defineComponent } from 'vue'
import { Popper as ElPopper } from '@element-plus/popper'

import type { PropType } from 'vue'
import type { Effect, Placement, Options } from '@element-plus/popper/src/popper'
export default defineComponent({
  name: 'ElTooltip',
  components: {
    ElPopper,
  },
  props: {
    effect: {
      type: String as PropType<Effect>,
      default: 'dark' as Effect,
    },
    content: {
      type: String,
      default: '',
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    enterable: {
      type: Boolean,
      default: true,
    },
    hideAfter: {
      type: Number,
      default: 0,
    },
    manual: {
      type: Boolean,
      default: false,
    },
    modelValue: {
      type: Boolean,
      validator: val => {
        return typeof val === 'boolean'
      },
    },
    offest: {
      type: Number,
      default: 0,
    },
    // This API should be decaprecate since it's confusing with close-delay
    openDelay: {
      type: Number,
      default: 0,
    },
    placement: {
      type: String as PropType<Placement>,
      default: 'bottom' as Placement,
    },
    // Once this option were given, the entire popper is under the users' control, top priority
    popperOptions: {
      type: Object as PropType<Options>,
      default: () => null,
    },
    // Alias for open-delay, which controls the popper's appearing time
    showAfter: {
      type: Number,
      default: 0,
    },
    tabindex: {
      type: Number,
      default: 0,
    },
    transition: {
      type: String,
      default: 'el-fade-in-linear',
    },
    value: {
      type: Boolean,
    },
    visibleArrow: {
      type: Boolean,
      default: false,
    },
  },
  emits: ['update:modelValue'],
  setup(props) {
    // init here
  },
})
</script>
<style scoped>
</style>
