<template>
    <div>
        <h1>New Warehouse</h1>

        <div class="container">
            
            <v-alert type="info" v-if="msg != null">
                <p>{{ msg }}</p>
            </v-alert>

            <form v-on:submit.prevent>


                <v-text-field label="Name" v-model="form.name"></v-text-field>
                <v-text-field label="Code" v-model="form.code"></v-text-field>
                <v-text-field label="Address" v-model="form.adress"></v-text-field>
                <v-text-field label="City" v-model="form.city"></v-text-field>
                <v-text-field label="Area m²" v-model="form.area"></v-text-field>
                <v-text-field label="CEP" v-model="form.cep"></v-text-field>
                <v-textarea label="Description" v-model="form.description"></v-textarea>

                <v-btn color="primary" v-on:click="postWarehouse">Save</v-btn>

            </form>
        </div>
    </div>
</template>

<script>
    export default{
        name: 'WarehouseNew',

        data(){
            return{
                msg: null,

                form:{
                    name: '',
                    adress: '',
                    city: '',
                    area: '',
                    cep: '',
                    description: '',
                    code: ''
                }
            }
        },

        methods:{
            async postWarehouse(){
                console.log('Attempting to post warehouse data', this.form);
                try {
                    await this.$http.post('http://localhost:3000/api/v1/warehouses', {
                        name: this.form.name,
                        adress: this.form.adress,
                        code: this.form.code,
                        city: this.form.city,
                        area: this.form.area,
                        cep: this.form.cep,
                        description: this.form.description
                    })

                    this.msg = 'Warehouse created successfully';
                } catch (error) {
                    console.log(error);
                }
            }
        }
    }
</script>

<style>
    .form {
        margin-bottom: 15px;
    }

    .form input {
        margin: 5px;
    }
</style>