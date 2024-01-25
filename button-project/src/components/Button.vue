<template>
  <component
    :is="buttonType"
    :href="buttonType === 'a' ? href : null"
    :to="buttonType === 'router-link' ? to : null"
    :tabindex="tabIndex"
    :class="buttonClasses"
    @click="handleClick"
  >
    <slot />
  </component>
</template>

<script setup lang="ts">
import { computed } from "vue";
import { defineProps, PropType, defineEmits } from "vue";

// Define the properties for the component
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
  colorVariant: {
    type: String,
    default: null,
  },
  to: {
    type: [String, Object],
    default: null,
  },
  href: {
    type: String,
    default: null,
  },
  block: Boolean,
  disabled: Boolean,
});

const emit = defineEmits(["click"]);

// Determine the button type based on the disabled state and tag
const buttonType = computed(() => (props.disabled ? "button" : props.tag));

// Calculate tabindex based on the disabled state
const tabIndex = computed(() => (props.disabled ? -1 : 0));

// Generate the class list for the button
const buttonClasses = computed(() => [
  "btn",
  `btn-${props.size}`,
  `btn-${props.variant}`,
  `btn-${props.colorVariant}`,
  { "btn-block": props.block, "btn-disabled": props.disabled },
]);

// Handle click events
const handleClick = (event: Event) => {
  if (!props.disabled) {
    emit("click", event);
  }
};
</script>

<style scoped>
/* Base styles for button, link, and router-link */
.btn,
.btn-a,
.btn-router-link {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  border: none;
  gap: 8px;
  font-family: "Montserrat", sans-serif;
}

/* Size Variants */
/* Small Button */
.btn-small,
.btn-a.btn-small,
.btn-router-link.btn-small {
  padding: 10px 16px;
  border-radius: 20px;
  font-size: 14px;
  font-style: normal;
  font-weight: 500;
  line-height: 140%;
  letter-spacing: -0.42px;
}

/* Regular Button */
.btn-regular,
.btn-a.btn-regular,
.btn-router-link.btn-regular {
  padding: 14px 24px;
  border-radius: 24px;
  font-size: 16px;
  font-style: normal;
  font-weight: 500;
  line-height: 125%;
  letter-spacing: -0.48px;
}

/* Large Button */
.btn-large,
.btn-a.btn-large,
.btn-router-link.btn-large {
  padding: 16px 24px;
  border-radius: 28px;
  font-size: 18px;
  font-style: normal;
  font-weight: 500;
  line-height: 135%;
  letter-spacing: -0.54px;
}

/* Color Variants */
/* Orange Button */
.btn-orange,
.btn-a.btn-orange,
.btn-router-link.btn-orange {
  background-color: var(--btn-orange);
  color: black;
}

/* Hover and Focus - Orange Button */
.btn-orange:not(.btn-disabled):hover,
.btn-a.btn-orange:not(.btn-disabled):hover,
.btn-router-link.btn-orange:not(.btn-disabled):hover,
.btn-orange:not(.btn-disabled):focus,
.btn-a.btn-orange:not(.btn-disabled):focus,
.btn-router-link.btn-orange:not(.btn-disabled):focus {
  background-color: var(--btn-orange-hover);
}

/* Dark Orange Button */
.btn-dark-orange,
.btn-a.btn-dark-orange,
.btn-router-link.btn-dark-orange {
  background-color: var(--btn-dark-orange);
  color: white;
}

/* Hover and Focus - Dark Orange Button */
.btn-dark-orange:not(.btn-disabled):hover,
.btn-a.btn-dark-orange:not(.btn-disabled):hover,
.btn-router-link.btn-dark-orange:not(.btn-disabled):hover,
.btn-dark-orange:not(.btn-disabled):focus,
.btn-a.btn-dark-orange:not(.btn-disabled):focus,
.btn-router-link.btn-dark-orange:not(.btn-disabled):focus {
  background-color: var(--btn-dark-orange-hover);
}

/* Green Button */
.btn-green,
.btn-a.btn-green,
.btn-router-link.btn-green {
  background-color: var(--btn-green);
  color: white;
}

/* Hover and Focus - Green Button */
.btn-green:not(.btn-disabled):hover,
.btn-a.btn-green:not(.btn-disabled):hover,
.btn-router-link.btn-green:not(.btn-disabled):hover,
.btn-green:not(.btn-disabled):focus,
.btn-a.btn-green:not(.btn-disabled):focus,
.btn-router-link.btn-green:not(.btn-disabled):focus {
  background-color: var(--btn-green-hover);
}

/* Dark Green Button */
.btn-dark-green,
.btn-a.btn-dark-green,
.btn-router-link.btn-dark-green {
  background-color: var(--btn-dark-green);
  color: white;
}

/* Hover and Focus - Dark Green Button */
.btn-dark-green:not(.btn-disabled):hover,
.btn-a.btn-dark-green:not(.btn-disabled):hover,
.btn-router-link.btn-dark-green:not(.btn-disabled):hover,
.btn-dark-green:not(.btn-disabled):focus,
.btn-a.btn-dark-green:not(.btn-disabled):focus,
.btn-router-link.btn-dark-green:not(.btn-disabled):focus {
  background-color: var(--btn-dark-green-hover);
}

/* Red Button */
.btn-red,
.btn-a.btn-red,
.btn-router-link.btn-red {
  background-color: var(--btn-red);
  color: white;
}

/* Hover and Focus - Red Button */
.btn-red:not(.btn-disabled):hover,
.btn-a.btn-red:not(.btn-disabled):hover,
.btn-router-link.btn-red:not(.btn-disabled):hover,
.btn-red:not(.btn-disabled):focus,
.btn-a.btn-red:not(.btn-disabled):focus,
.btn-router-link.btn-red:not(.btn-disabled):focus {
  background-color: var(--btn-red-hover);
}

/* Outlined Button */
.btn-outlined,
.btn-a.btn-outlined,
.btn-router-link.btn-outlined {
  background-color: var(--btn-outlined);
  color: var(--btn-outlined-border);
  border: 1px solid var(--btn-outlined-border);
}

/* Hover and Focus - Outlined Button */
.btn-outlined:not(.btn-disabled):hover,
.btn-a.btn-outlined:not(.btn-disabled):hover,
.btn-router-link.btn-outlined:not(.btn-disabled):hover,
.btn-outlined:not(.btn-disabled):focus,
.btn-a.btn-outlined:not(.btn-disabled):focus,
.btn-router-link.btn-outlined:not(.btn-disabled):focus {
  background-color: var(--btn-outlined-hover);
}

/* Block style */
.btn-block,
.btn-a.btn-block,
.btn-router-link.btn-block {
  width: 100%;
  text-align: center;
}

/* Disabled style */
.btn-disabled,
.btn-a.btn-disabled,
.btn-router-link.btn-disabled {
  opacity: 0.4;
  pointer-events: none;
  cursor: not-allowed;
}
</style>
