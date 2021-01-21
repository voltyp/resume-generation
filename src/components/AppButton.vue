<template>
  <button class="btn" :class="color" >
    <slot />
  </button>
</template>

<script>
export default {
  name: "AppButton",
  props: {
    color: {
      type: String,
      required: true
    }
  }
}
</script>
