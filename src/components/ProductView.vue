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
        <!-- <form>
            <label for="product">Name Product: </label>
            <input type="text" id="product" v-model="product">

            <label for="price">Price: </label>
            <input type="number" id="price" v-model="price">

            <label for="discount">Discount: </label>
            <input type="number" id="discount" v-model="discount">

            <label for="number">Number: </label>
            <input type="number" id="number" v-model="number">
        </form>

        <div>
            <p><b> Product: </b><span> {{ product }} </span></p>
            
            <p><b> First Price: </b><span> {{ price | toman }} </span></p>
            
            <p><b> Price with discount: </b><span> {{ cost }} </span></p>
            
            <p><b> Your Price: </b><span> {{ payable | toman }} </span></p>
        </div>
        <br> -->
        <!--  -->
        <hr>
        <div class="container py-4">

            <div class="">
                <button type="button" class="btn btn-info btn-sm"> new item + </button>
            </div>
            <form class="row" v-for="p in products" :key="p.name"> 
                
                <div class="col-md-3">
                    <label for="product">Name Product: </label>
                    <input type="text" class="form-control" id="product" v-model="p.name">
                </div>

                <div class="col-md-3">
                    <label for="price">Price: </label>
                    <input type="number" class="form-control" id="price" v-model="p.price">
                </div>

                <div class="col-md-3">
                    <label for="discount">Discount: </label>
                    <input type="number" class="form-control" id="discount" v-model="p.discount">
                </div>

                <div class="col-md-3">
                    <label for="number">Number: </label>
                    <input type="number" class="form-control" id="number" v-model="p.number">
                </div>

            </form>

            <table class="table">
                <thead>
                    <tr>
                        <th> name </th>
                        <th> first price </th>
                        <th> price with discount </th>
                        <th> your price </th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td> {{ name }} </td>
                        <td> {{ price | toman }} </td>
                        <td> {{ cost }} </td>
                        <td> {{ payable | toman }} </td>
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
            cost : function() {
                return this.price - (this.discount * this.price / 100)
            },
            payable : function() {
                return this.number * this.cost
            },
        },

        filters : {
            toman : function(value){
                return value != 0 ? value.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",") + "T" : value;
            },
        },

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

                // product : null,
                // price : 0,
                // discount : 0,
                // number : 1,

                products : [
                    {
                        name : null,
                        price : 0,
                        discount : 0,
                        number : 1
                    }
                ]
            }
        },

        mounted : function () {
            axios.get('http://api.open-notify.org/astros.json').then(res => this.list = res.data.people);
        },
    }
</script>

<style>

</style>