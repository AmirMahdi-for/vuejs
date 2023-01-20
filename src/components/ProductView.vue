<template>
    <div>
        {{ message }}
        <br>
        <!-- LEARN OBJECT -->
        {{ my_data.name }}
        <br>
        <!-- LEARN V-FOR -->
        <a :href="my_data.web_url">THIS IS GOOGLE</a>
        <br>
        <table>
            <thead>
                <tr>
                    <th>id</th>
                    <th>Name</th>
                    <th>Age</th>
                    <th>Job</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="person, i in people" :key="person.id">
                    <td> {{ i+1 }} </td>
                    <td> {{ person.firstName + ' ' + person.lastName }} </td>
                    <td> {{ person.age }} </td>
                    <td> {{ person.job }} </td>
                </tr>
            </tbody>
        </table>
        <br>
        <!-- LEARN V-IF -->
        <div v-if="list.length < 0">
            <div v-for="person in list" :key="person.name">
                <h2> {{ person.name }} </h2>
                <p>craft : <span>{{person.craft}}</span></p>
            </div>
        </div>
        <div v-else>
            Loading
        </div>
        <br>
        <!-- LEARN COMPUTED AND FILTER -->
        <hr>
        <div class="container py-4">

            <div class="">
                <button type="button" class="btn btn-info btn-sm" @click="newProduct"> new item + </button>
            </div>
            <form class="row" v-for="p, i in products" :key="p.name"> 
                
                <div class="col-md-3">
                    <label for="product">Name Product: </label>
                    <input type="text" class="form-control" id="product" v-model="p.name">
                </div>

                <div class="col-md-2">
                    <label for="price">Price: </label>
                    <input type="number" class="form-control" id="price" v-model="p.price">
                </div>

                <div class="col-md-2">
                    <label for="discount">Discount: </label>
                    <input type="number" class="form-control" id="discount" v-model="p.discount">
                </div>

                <div class="col-md-2">
                    <label for="number">Number: </label>
                    <input type="number" class="form-control" id="number" v-model="p.number">
                </div>

                <div class="col-md-3 align-self-center">
                    <button type="button" class="btn btn-danger btn-sm" @click="deleteProduct(i)">Delete item</button>
                </div>

            </form>

            <table class="table mt-4">
                <thead>
                    <tr>
                        <th> id </th>
                        <th> name </th>
                        <th> first price </th>
                        <th> price with discount </th>
                        <th> your price </th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="p, i in products" :key="p.name">
                        <td> {{ i+1 }} </td>
                        <td> {{ p.name }} </td>
                        <td> {{ p.price }} </td>
                        <td> {{ cost(p.price, p.discount) }} </td>
                        <td> {{ cost(p.price, p.discount) * p.number }} </td>
                    </tr>
                    <tr v-for="product in products" :key="product.name">
                        <td align="center" colspan="3"> Sum of Price </td>
                        <td align="center" colspan="2"> {{ sumPrice }} </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    export default {
        computed : {
            // cost : function() {
            //     return this.products.price - (this.products.discount * this.products.price / 100)
            // },
            // payable : function() {
            //     return this.products.number * this.cost
            // },
        },

        methods : {
            deleteProduct : function(index) {
                this.products.splice(index, 1);
            },
            newProduct : function() {
                this.products.push(
                    {
                        name : null,
                        price : 0,
                        discount : 0,
                        number : 1 
                    }
                )
            },
            cost : function(price, discount) {
                return price - (discount * price / 100)
            },
            sumPrice : function() {
                // eslint-disable-next-line no-unused-vars
                let products = this.products
                // eslint-disable-next-line no-unused-vars
                let sum  = 0;
                for (var i = 0; i < products.length; i++){
                    // eslint-disable-next-line no-unused-vars
                    sum += this.cost(products[i].price, products[i].discount) * products[i].number;
                }
                return sum;
            }
        },

        // filters : {
        //     toman : function(value){
        //         return value != 0 ? value.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",") + "T" : value;
        //     },
        // },

        data()  {
            return {
                message : 'HelloVueJs',

                my_data : {
                    name : 'amir mahdi',
                    age : '20',
                    web_url : 'http:///google.com',
                },

                people : [
                    {
                        id : 'a',
                        firstName : 'Amir',
                        lastName : 'Fakhri',
                        age : '28',
                        job : 'Co-founder'
                    },
                    {
                        id : 'b',
                        firstName : 'Kamand',
                        lastName : 'Soleymani',
                        age : '25',
                        job : 'Manager'
                    },
                    {
                        id : 'c',
                        firstName : 'Nilo',
                        lastName : 'Tahmasb',
                        age : '27',
                        job : 'Developer'
                    },
                ],

                list : [],



                products : [
                    {
                        name : null,
                        price : 0,
                        discount : 0,
                        number : 1,
                        sum : 0,
                    }
                ]
            }
        },

        mounted : function () {
            axios.get('http://api.open-notify.org/astros.json').then(res => this.list = res.data.people)
        },
    }
</script>

<style>

</style>