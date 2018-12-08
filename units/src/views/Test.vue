<template>
  <div>
    <button class="button is-info are-small" @click="toggleModal = true">Esto es un test</button>
    <hr>
    <div>
      <div class="modal" :class="{'is-active': toggleModal}">
        <div class="modal-background"></div>
        <div class="modal-card">
          <header class="modal-card-head">
            <p class="modal-card-title">Modal title</p>
            <button class="delete" aria-label="close" @click="toggleModal = false"></button>
          </header>
          <section class="modal-card-body">
            <!-- Content ... -->
          </section>
          <footer class="modal-card-foot">
            <button @click="toggleModal = false" class="button is-success">Save changes</button>
            <button @click="toggleModal = false" class="button">Cancel</button>
          </footer>
        </div>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
@Component /* ({
  template: require('@/views/templates/templateTest.html'),
}) */
export default class Test extends Vue {
  toggleModal = false;
}
</script>
