<template>
  <div class="app-view">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- Type -->
    <div class="flx-container">
      <div class="flx-center">
        <div class="select">
          <select v-model="idSelectedDT">
            <option value="null" disabled selected>Choose your option</option>
            <option v-for="dType in dataType" :value="dType.id">{{dType.name}}</option>
          </select>
        </div>
      </div>
    </div>
    <!-- From -->
    <div v-if="idSelectedDT != null" class="flx-container">
      <div class="flx-center">
        <div class="select">
          <select>
            <option value disabled selected>Choose your option</option>
            <option v-for="dataFormat in actualDataTypeList">{{dataFormat}}</option>
          </select>
        </div>
      </div>
    </div>
    <!-- To -->
  </div>
</template>

<script lang="ts">
import { Component, Vue, Watch } from 'vue-property-decorator';

@Component({
  components: {},
})
export default class Home extends Vue {
  private actualDataTypeList = [];
  private idSelectedDT: number = null;
  private dataType: any = [
    {
      type: 'length',
      id: 0,
      name: 'Longitud',
      list: ['metro', 'yarda', 'milla'],
    },
    {
      type: 'time',
      id: 1,
      name: 'Tiempo',
      list: [],
    },
    {
      type: 'mass',
      id: 2,
      name: 'Massa',
      list: [],
    },
    {
      type: 'electricIntensity',
      id: 3,
      name: 'Intensidad electrica',
      list: [],
    },
    {
      type: 'temperature',
      id: 4,
      name: 'Temperatura',
      list: [],
    },
    {
      type: 'substance',
      id: 5,
      name: 'Temperatura',
      list: [],
    },
    {
      type: 'lightIntensity',
      id: 6,
      name: 'Intensidad lumínica',
      list: [],
    },
    {
      type: 'force',
      id: 7,
      name: 'Fuerza',
      list: [],
    },

    {
      type: 'energy',
      id: 8,
      name: 'Energía',
      list: [],
    },

    {
      type: 'density',
      id: 9,
      name: 'Densidad',
      list: [],
    },
    {
      type: 'data',
      id: 10,
      name: 'Datos',
      list: [],
    },
  ];

  @Watch('idSelectedDT')
  onIdSelectedDTChanged(value: number, oldValue: number) {
    // Cada vez que canvia el tipo de dato pon la lista de datos en el select
    if (value != null) {
      this.test(value);
    }
  }
  private test(_v: number) {
    let _list = this.dataType.find(el => {
      if (el.id === _v) {
        return el.list;
      }
    });
    this.actualDataTypeList = _list.list;
    console.log(_v, this.actualDataTypeList, this.dataType, this.idSelectedDT);
  }
}
</script>
