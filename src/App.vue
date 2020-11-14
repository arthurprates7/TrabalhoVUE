<template>
  <div>
    <b-container class="text-center">
      <h2>Cadastro de Produtos</h2>
      <h4>Trabalho de Faculdade para treinar Componentização com Vue.js</h4>
    </b-container>
    

    <div>
    <b-tabs content-class="mt-3">
      <b-tab title="Lista de Produtos" active>
        
        <list :listdata="items"/>

      </b-tab>
      <b-tab title="Cadastro">
        
          <register @pushItem="getPushItem"/>

      </b-tab>
    </b-tabs>
  </div>
    
  

  </div>
</template>

<script>
import { List, Register } from "@/views";

export default {

  data: () =>{

    return {

      items: [

        {

          'name': 'Cesta de Frutas', 
          'price': 22.00

        },{

          'name': 'Catálogo de Produtos', 
          'price': 21.00

        },{

          'name': 'Curso udemy', 
          'price': 20.00

        }

      ]

    }

  },

  name: "App",
  
  components: {
    'list':List,
    'register':Register,

  },

  methods: {

    getPushItem( value ){

      this.items.push(value)

    }

  }
};
</script>

<style></style>
