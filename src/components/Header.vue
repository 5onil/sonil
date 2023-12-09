<template>
  <header class="header">
    <div class="logo">
      <img src="../assets/logo.svg" alt="logo" />
    </div>
    <nav class="navigation">
      <RouterLink to="/">Hello</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
  </header>
  <RouterView />
</template>

<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<style scoped lang="scss">
.header {
  display: flex;
}
.logo {
  display: flex;
  img {
    width: 60px;
  }
}
.navigation {
  margin-left: -60px;
  display: flex;
  gap: 20px;
  align-items: center;
  justify-content: center;
  flex-grow: 1;
  a {
    position: relative;
    color: #000;
    border: 2px solid #000;
    padding: 7px 20px;

    background: transparent;
    &:after {
      content: '';
      position: absolute;
      width: calc(100% + 4px);
      height: calc(100% + 4px);
      border: 2px solid #000;
      top: -7px;
      left: -10px;
      pointer-events: none;
      background: transparent;
      transition: all 0.2s ease-out;
    }
    &:hover {
      color: #fff;
      background-color: #000;

      &:after {
        top: 3px;
        left: 6px;
      }
    }
    &:active {
      &:after {
        top: -2px;
        left: -2px;
      }
    }
  }
  .router-link-active {
    color: #fff;
    background-color: #000;
  }
}

@media (min-width: 1176px) {
  .logo {
    padding: 20px 0 0 20px;
  }
  .navigation {
    margin-left: -80px;
    gap: 44px;
    a {
      padding: 10px 40px;
    }
  }
}
</style>
