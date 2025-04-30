<script setup>
/**
 * @typedef {'button'|'submit'|'reset'} ButtonType
 * @typedef {{ disabled?: boolean, type?: ButtonType }} BaseBtnProps
 */

/** @type {BaseBtnProps} */
// eslint-disable-next-line no-undef
const props = defineProps({
  disabled: { type: Boolean, default: false },
  type:     { type: String,  default: 'button' },
})

const classes = [
  'base-btn',
  { 'is-disabled': props.disabled },
]
</script>

<template>
  <button
    :class="classes"
    :disabled="props.disabled"
    :type="props.type"
    v-bind="$attrs"
  >
    <slot />
  </button>
</template>

<style scoped>
.base-btn {
  padding: .5rem 1.25rem;
  border: none;
  border-radius: .333rem;
  font-weight: 600;
  cursor: pointer;
  background: #009688;
  color: #fff;
  transition: transform .15s, box-shadow .15s;
}
.base-btn:hover,
.base-btn:focus-visible {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgb(0 0 0 / .15);
}
.base-btn:active {
  transform: translateY(0);
  box-shadow: 0 2px 6px rgb(0 0 0 / .15);
}
.base-btn:disabled,
.is-disabled {
  opacity: .55;
  cursor: not-allowed;
  transform: none !important;
  box-shadow: none !important;
}
</style>
