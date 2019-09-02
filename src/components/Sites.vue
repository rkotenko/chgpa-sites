<style lang="scss">
  @import "../../node_modules/ag-grid-community/dist/styles/ag-theme-balham.css";
  @import "../../node_modules/ag-grid-community/dist/styles/ag-grid.css";
</style>

<template>
  <ag-grid-vue style="width: 100%; height: 500px;" 
    class="ag-theme-balham"
    :columnDefs="columnDefs"
    :rowData="rowData">
  </ag-grid-vue>
</template>

<script lang="ts">
  import { Component, Vue, Prop, Provide } from 'vue-property-decorator';
  import { data } from '../data/data.js';
  import { AgGridVue } from 'ag-grid-vue';

  @Component({
    components: { AgGridVue },
  })
  
  export default class Sites extends Vue {
    protected columnDefs: object;
    protected rowData: object;

    constructor() {
      super();
      this.columnDefs = data.headers;
      this.rowData = data.sites;
    }
  }
</script>