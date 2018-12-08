<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>|
      <router-link to="/test">Test</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style lang="less">
@import '~bulma/css/bulma.css';
input[type='text'] {
  margin: 6px;
}
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
header.modal-card-head {
  &.success {
    background-color: rgb(30, 141, 11);
    .modal-card-title {
      color: white !important;
    }
  }
  &.info {
    background-color: rgb(15, 124, 196);
    .modal-card-title {
      color: white !important;
    }
  }
  &.warning {
    background-color: rgb(221, 191, 20);
    .modal-card-title {
      color: black !important;
    }
  }
  &.danger {
    background-color: rgb(196, 15, 15);
    .modal-card-title {
      color: white !important;
    }
  }
}
</style>
