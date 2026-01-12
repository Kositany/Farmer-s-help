<script setup></script>

<template>
  <router-view />
</template>

<style>
:root {
  --jungle-green: #00a86b;
  --jungle-green-dark: #008557;
  --jungle-green-light: #00c77f;
  --dark-bg: #0a0a0a;
  --dark-bg-light: #1a1a1a;
  --dark-bg-lighter: #2a2a2a;
  --white: #ffffff;
  --white-muted: rgba(255, 255, 255, 0.9);
  --white-dim: rgba(255, 255, 255, 0.7);
  --white-subtle: rgba(255, 255, 255, 0.5);
  --black: #000000;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: #0a0a0a;
  color: #ffffff;
}

#app {
  background: #0a0a0a;
  min-height: 100vh;
}
</style>
