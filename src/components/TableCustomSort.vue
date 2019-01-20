<template>
  <div>
    <md-table v-model="data" :md-sort.sync="currentSort" 
    :md-sort-order.sync="currentSortOrder" :md-sort-fn="customSort" md-card>
      <md-table-toolbar>
        <h1 class="md-title">{{ data[0].file }}</h1>
      </md-table-toolbar>
       <md-table-row  slot="md-table-row"  slot-scope="{ item }">
     
       
     
         <md-table-cell md-label="File Name" md-sort-by="file">{{ item.file }}</md-table-cell>
        <md-table-cell md-label="Search Name" md-sort-by="type">{{ item.type }}</md-table-cell>
        <md-table-cell md-label="Pattern" md-sort-by="pattern">{{ item.pattern }}</md-table-cell>
        <md-table-cell md-label="Number" md-sort-by="len">{{ item.len }}</md-table-cell>
        
       
        <md-table-cell md-label="Time" md-sort-by="time" >{{ item.time }}</md-table-cell>
        
      
      </md-table-row>
        
    </md-table>
  </div>
</template>

<script>
  
  export default {
    name: 'TableCustomSort',
     props: {
        data: ''
      },
    data: () => ({
      currentSort: 'file  ',
     
      currentSortOrder: 'asc',
         
    }),
    methods: {
      customSort (value) {
        return value.sort((a, b) => {
          const sortBy = this.currentSort

          if (this.currentSortOrder === 'desc') {
            return a[sortBy].localeCompare(b[sortBy], undefined, { numeric: true, sensitivity: 'base' })
          }

          return b[sortBy].localeCompare(a[sortBy], undefined, { numeric: true, sensitivity: 'base' })
        })
      }
    }
  }
</script>