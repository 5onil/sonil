<template>
  <div class="project">
    <se-background-bubble class="bg-bubble" />
    <div class="project-content">
      <h2>{{ projectHeading }}</h2>
      <p>{{ aboutText }}</p>
    </div>
  </div>
</template>

<script setup>
import SeBackgroundBubble from './BackgroundBubble.vue'
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
  flex: 1;
  position: relative;
  background-color: #000;
  color: #fff;
  padding: 25px;
  h2 {
    text-transform: uppercase;
  }
  .project-content {
    position: relative;
    z-index: 200;
    cursor: pointer;
  }
}
.project:after {
  position: absolute;
  z-index: 100;
  top: 0;
  left: 0;
  content: '';
  display: block;
  width: 100%;
  height: 100%;
  outline: 2px solid transparent; /* Initial transparent outline */
  outline-offset: -10px;
  animation: animateOutline 4s linear forwards;
}
.bg-bubble {
  opacity: 0;
  transition: opacity 0.3s linear;
}
.bg-bubble:has(+ .project-content:hover) {
  opacity: 1;
}

@keyframes animateOutline {
  0% {
    outline-color: transparent; /* Start with transparent outline */
  }
  25% {
    outline-color: #fff; /* Draw top right */
  }
  50% {
    outline-color: #fff; /* Draw bottom right */
  }
  75% {
    outline-color: #fff; /* Draw bottom left */
  }
  100% {
    outline-color: #fff; /* Draw top left */
  }
}
</style>
