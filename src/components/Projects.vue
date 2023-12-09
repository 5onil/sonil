<template>
  <div class="project">
    <h2>{{ projectHeading }}</h2>
    <p>{{ aboutText }}</p>
  </div>
</template>

<script setup>
const props = defineProps({
  translations: {
    type: Object,
    required: true
  }
})

// Translations
const { projectHeading, aboutText } = props.translations
</script>

<style scoped lang="scss">
.project {
  background-color: #000;
  color: #fff;
  padding: 15px;
  h2 {
    text-transform: uppercase;
  }
}
</style>
