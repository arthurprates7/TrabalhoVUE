<template>
  <div>
    
    <b-table 
      striped 
      hover
      :fields="fields"
      :items="items" 
      
      />
   
  </div>
  
</template>
<script>

  import { BTable } from "bootstrap-vue";

  export default{

    props: {

      listdata: {
        
        type: Array,
        required: true,
        validator: (value) =>{

          if (typeof value === 'undefined')
            return false;

          return true;


        }
      
      }

    },

    components:{

      BTable

    },

    data(){

      return{

        items: this.listdata, 

        fields:[

          {
            key: 'name', 
            label: 'Nome:', 
            sortable: 'true'
          },
          {
            key: 'price', 
            label: 'Preço:',
            sortable: true
          }

        ]

      }

    }

  }  

</script>