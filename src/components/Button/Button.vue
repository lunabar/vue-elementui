<template>
  <button ref="_ref" class="vk-button" :class="{
    [`vk-button--${type}`]: type,
    [`vk-button--${size}`]: size,
    'is-plain': plain,
    'is-round': round,
    'is-circle': circle,
    'is-disabled': disabled,
  }" :disabled="disabled" :type="nativeType" :autofocus="autofocus">
    <span>
      <slot />
    </span>
  </button>

</template>

<script setup lang="ts">
// import { buttonProps } from './types'; 
import type { ButtonProps } from './types';
import { ref } from 'vue';
// defineProps(buttonProps)
defineOptions({
  name: 'VButton',
})
withDefaults(defineProps<ButtonProps>(), {
  nativeType: 'button',
})
const _ref = ref<HTMLButtonElement>()
defineExpose({
  ref: _ref,
})



</script>

<style></style>