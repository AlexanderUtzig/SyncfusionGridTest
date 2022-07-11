<template>
  <div id="app">
    <ejs-grid
      id='Grid'
      :dataSource='srcData'
      :allowSelection="true"
      :allowRowDragAndDrop="true"
      width="100%">
      <e-columns>
        <e-column field='OrderID' headerText='Order ID' width='120' textAlign='Right'></e-column>
        <e-column field='CustomerID' headerText='Customer Name' width='130'></e-column>
        <e-column field='Freight' headerText='Freight' width='120' format='C2' textAlign='Right'></e-column>
      </e-columns>
    </ejs-grid>
  </div>
</template>
<script>
import { defineComponent, ref } from 'vue';
import {
  ColumnDirective,
  ColumnsDirective,
  GridComponent,
} from '@syncfusion/ej2-vue-grids';
import {
  RowDD,
  Selection,
} from '@syncfusion/ej2-grids';

export default defineComponent ({
  name: 'SyncfusionGrid',
  components: {
    'e-column': ColumnDirective,
    'e-columns': ColumnsDirective,
    'ejs-grid': GridComponent,
  },
  provide: {
    grid: [RowDD, Selection]
  },
  setup() {
    const srcData = ref([{
      "OrderID":10248,
      "CustomerID":"VINET",
      "OrderDate":"1996-07-04T00:00:00.000Z",
      "ShippedDate":"1996-07-16T00:00:00.000Z",
      "Freight":32.38,
      "ShipName":"Vins et alcools Chevalier",
      "ShipAddress":"59 rue de l'Abbaye",
      "ShipCity":"Reims",
      "ShipRegion":null,
      "ShipCountry":"France",
      "Verified": true
    },
      {
        "OrderID":10249,
        "CustomerID":"TOMSP",
        "OrderDate":"1996-07-05T00:00:00.000Z",
        "ShippedDate":"1996-07-10T00:00:00.000Z",
        "Freight":11.61,
        "ShipName":"Toms Spezialitäten",
        "ShipAddress":"Luisenstr. 48",
        "ShipCity":"Münster",
        "ShipRegion":null,
        "ShipCountry":"Germany"
      },
      {
        "OrderID":10250,
        "CustomerID":"HANAR",
        "OrderDate":"1996-07-08T00:00:00.000Z",
        "ShippedDate":"1996-07-12T00:00:00.000Z",
        "Freight":65.83,
        "ShipName":"Hanari Carnes",
        "ShipAddress":"Rua do Paço, 67",
        "ShipCity":"Rio de Janeiro",
        "ShipRegion":"RJ",
        "ShipCountry":"Brazil",
        "Verified": true
      },
      {
        "OrderID":10251,
        "CustomerID":"VICTE",
        "OrderDate":"1996-07-08T00:00:00.000Z",
        "ShippedDate":"1996-07-15T00:00:00.000Z",
        "Freight":41.34,
        "ShipName":"Victuailles en stock",
        "ShipAddress":"2, rue du Commerce",
        "ShipCity":"Lyon",
        "ShipRegion":null,
        "ShipCountry":"France",
        "Verified": true
      }]);

    return {
      srcData,
    };
  },
})
</script>
<style>
@import "../../node_modules/@syncfusion/ej2-vue-grids/styles/material.css";
</style>
