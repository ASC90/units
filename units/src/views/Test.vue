<template>
  <div>
    <button class="button is-info are-small" @click="toggleModal = true">Esto es un test</button>
    <div style="width: 50%">
      <input class="input is-primary" type="text" v-model="indexModalInit">
      <input class="input is-primary" type="text" v-model="msg">
      <input class="input is-primary" type="text" v-model="title">
    </div>
    <hr>
    <Modal
      :modalMSG="msg"
      :modalTitle="title"
      :isDialogOpen="toggleModal"
      v-on:closeDialog="toggleModal = false"
      :modalTypeIndex="indexModalInit"
      @modalTypeIndexChange="onChangeIndexModal"
    ></Modal>
  </div>
</template>
<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import Modal from '@/components/Modal.vue';
@Component({
  components: {
    Modal,
  },
}) /* ({
  template: require('@/views/templates/templateTest.html'),
}) */
export default class Test extends Vue {
  msg = 'Esto es un mensaje de ejemplo';
  title = 'Machacasaurio';
  indexModalInit = 1;
  toggleModal = false;
  onChangeIndexModal(val: number) {
    this.indexModalInit = val;
  }
}
</script>
