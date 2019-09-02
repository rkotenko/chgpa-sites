<style lang="scss">
  @import "./node_modules/ag-grid-community/dist/styles/ag-grid.css";
  @import "./node_modules/ag-grid-community/dist/styles/ag-theme-balham.css";
</style>

<template>
  <ag-grid-vue style="width: 500px; height: 500px;"
                 class="ag-theme-balham"
                 :columnDefs="columnDefs"
                 :rowData="rowData">
  </ag-grid-vue>
</template>

<script lang="ts">
  import { Component, Vue, Prop, Provide } from 'vue-property-decorator'
  import data from './data.js'
  import { AgGridVue } from "ag-grid-vue"

  @Component({
    components: { AgGridVue }
  })
  export default class App extends Vue {
    columnDefs: object;
    rowData: object;

    constructor() {
      super();
      
      this.columnDefs = data.headers;

      this.rowData = data.sites;

    }
  }
</script>