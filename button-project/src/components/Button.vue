<template>
  <component
    :is="buttonType"
    :class="[
      'btn',
      `btn-${size}`,
      `btn-${variant}`,
      { 'btn-block': block, 'btn-disabled': disabled },
    ]"
    @click="handleClick"
  >
    <slot />
  </component>
</template>

<script setup lang="ts">
import { ref, computed } from "vue";
import { defineProps, PropType } from "vue";

const props = defineProps({
  tag: {
    type: String as PropType<"button" | "a" | "router-link">,
    default: "button",
  },
  size: {
    type: String as PropType<"small" | "regular" | "large">,
    default: "regular",
  },
  variant: {
    type: String as PropType<"filled" | "outlined">,
    default: "filled",
  },
  block: Boolean,
  disabled: Boolean,
});

const buttonType = computed(() => (props.disabled ? "button" : props.tag));

const handleClick = (event: Event) => {
  if (!props.disabled) {
    // emit("click", event);
  }
};
</script>

<style scoped>
.btn {
}
.btn-small {
}
.btn-regular {
}
.btn-large {
}
.btn-filled {
}
.btn-outlined {
}
.btn-block {
}
.btn-disabled {
}
</style>
