<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style lang="less">
@import "~bulma/css/bulma.css";
.app-view {
  min-height: 100vh;
}
.flx-container {
  display: flex;
  flex-flow: wrap;
  .flx-center {
    margin: auto;
  }
}
</style>
