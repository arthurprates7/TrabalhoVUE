<template>
  <div>
    
    <b-container>

      <b-row class="justify-content-md-center mt-4">

        <b-col col md="8">

          <b-card 
            
          >
          
          <b-card-text>
            <b-form @submit="handleSubmit">

              <b-form-group 
                label="Nome do Produto:">

                <b-form-input
                v-model="name"
                required
                >
                </b-form-input>

              </b-form-group>

              <b-form-group 
               
                label="Qual o Preço deste produto?">

                <b-form-input
                v-model="price"
                required
                type="number"
                min=1
                >
                </b-form-input>

              </b-form-group>

              <b-form-group>

                <b-button
                block variant="primary"
                type="submit"
               

                
                >

                  Cadastro

                </b-button>

              </b-form-group>

            </b-form>
          </b-card-text>
          
          </b-card>

        </b-col>

      </b-row>

    </b-container>
   
  </div>
  
</template>
<script>

  export default{

    data(){

      return{

        name: '',
        price: ''

      }

    },
    methods: {

      handleSubmit(event){

        event.preventDefault();
        
        let product = {

          name: this.name,
          price: this.price

        };

        this.$emit('pushItem', product);

        alert('Produto Salvo com Sucesso')
        this.name = '';
        this.price = '';
        

      }

    }

  }
 
</script>