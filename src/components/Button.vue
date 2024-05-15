<script setup lang="ts">
import { BaseProps } from "@/types";
import { ref, reactive } from "vue";

export interface ButtonProps extends BaseProps {
  // color
  isPrimary?: boolean;
  isLink?: boolean;
  isInfo?: boolean;
  isSuccess?: boolean;
  isWarning?: boolean;
  isDanger?: boolean;
  //size
  isSmall?: boolean;
  isMedium?: boolean;
  isLarge?: boolean;
  // style
  isOutlined?: boolean;
  isLoading?: boolean;
  disabled?: boolean;
}

const props = defineProps<ButtonProps>();

const classObject = reactive({
  button: true,
  "is-primary": props.isPrimary,
  "is-link": props.isLink,
  "is-info": props.isInfo,
  "is-success": props.isSuccess,
  "is-warning": props.isWarning,
  "is-danger": props.isDanger,
  "is-small": props.isSmall,
  "is-medium": props.isMedium,
  "is-large": props.isLarge,
  "is-outlined": props.isOutlined,
  "is-loading": props.isLoading,
});

let disabled = ref(props.disabled);
</script>

<template>
  <button :disabled :class="[classObject, props['class']]">
    <slot></slot>
  </button>
</template>
