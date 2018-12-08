<template>
  <div>
    <div class="modal" :class="{'is-active': isDialogOpen, }">
      <div class="modal-background"></div>
      <div class="modal-card">
        <header class="modal-card-head" :class="[modalType[modalTypeIndex]]">
          <p class="modal-card-title">{{modalTitle}}</p>
          <button class="delete" aria-label="close" @click="onCloseModal()"></button>
        </header>
        <section class="modal-card-body">
          <button
            class="button is-link"
            @click="onChangeModalType(0)"
            :class="{'is-loading': modalTypeIndex == 0 ? true : false}"
          >0</button>
          <button
            class="button is-link"
            @click="onChangeModalType(1)"
            :class="{'is-loading': modalTypeIndex == 1 ? true : false}"
          >1</button>
          <button
            class="button is-link"
            @click="onChangeModalType(2)"
            :class="{'is-loading': modalTypeIndex == 2 ? true : false}"
          >2</button>
          <button
            class="button is-link"
            @click="onChangeModalType(3)"
            :class="{'is-loading': modalTypeIndex == 3 ? true : false}"
          >3</button>
          <div>{{modalMSG}}</div>
        </section>
        <footer class="modal-card-foot">
          <button @click="onCloseModal()" class="button is-success">Save changes</button>
          <button @click="onCloseModal()" class="button">Cancel</button>
        </footer>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
@Component
export default class Modal extends Vue {
  @Prop() private modalTypeIndex: number;
  @Prop() private modalMSG: string;
  @Prop() private modalTitle: string;
  @Prop() private isDialogOpen: boolean;
  modalType = ['success', 'info', 'warning', 'danger'];
  onCloseModal() {
    this.$emit('closeDialog');
  }
  onChangeModalType(val: number) {
    this.$emit('modalTypeIndexChange', val);
  }
}
</script>

