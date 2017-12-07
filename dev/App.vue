<template>
  <div>
    <vue-good-table
      :paginate="true"
      :columns="columns" 
      :rows="rows" 
      :columnTotals="true"
      :line-numbers="true"
      :onClick="onClick">
      <template slot="table-row-before" slot-scope="props">
        <td><input type="checkbox" /></td>
      </template>
      <template slot="table-row-after" slot-scope="props">
        <td><a class="button lightbox" :href="'test_detail.php?id=' + props.row.id" >detail</a></td>
      </template>
    </vue-good-table>
  </div>
</template>

<script>
  import Vue from 'vue';
  import VueGoodTable from '../src/index';
  Vue.use(VueGoodTable);
  export default {
    name: 'test',
    data(){
      return {
        columns: [
          {
            label: '',
            sortable: false,
          },
          {
            label: 'Name',
            field: 'name',
            type: 'text',
            filterable: true
          }, 
          {
            label: 'Age',
            field: 'age',
            type: 'number',
            summarizable: true,
            filterable: true
          }, 
          {
            label: 'Loss',
            field: 'loss',
            type: 'number',
            summarizable: true,
            filterable: true,
            type: 'decimal'
          }, 
          {
            label: '',
            sortable: false,
          },
        ],
        rows: [
          {
            name: "John",
            age: "20",
            loss : 52.40
          }, {
            name: "Jane",
            age: "24",
            loss : 17.10
          }, 
          {
            name: "Susan",
            age: "16",
            loss : 39.60
          }, 
          {
            name: "Chris",
            age: "55",
            loss : 27.92
          }, 
          {
            name: "Dan",
            age: "40",
            loss : 113.24
          }, 
          {
            name: "John",
            age: "20",
            loss : 69.34
          }, 
          {
            name: "Jane",
            age: "24",
            loss : 44.12
          }, 
          {
            name: "Susan",
            age: "16",
            loss : 56.98
          }, 
          {
            name: "Chris",
            age: "55",
            loss : 44.40
          }, 
          {
            name: "Dan",
            age: "40",
            loss : 72.15
          }, 
          {
            name: "Jane",
            age: "24",
            loss : 98.55
          }, 
          {
            name: "Susan",
            age: "16",
            loss : 45.14
          }, 
          {
            name: "Chris",
            age: "55",
            loss : 33.30
          }, 
          {
            name: "Dan",
            age: "40",
            loss : 17.18
          }, 
        ],
      };
    },
    methods: {
      onClick() {
        console.log('clicked');
      }
    }
  };
</script>

<style lang="css">
  .row-style{
    background-color: red;
  }
</style>

