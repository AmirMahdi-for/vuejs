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
        <div v-if="list.length > 0">
            <div v-for="person in list" :key="person.name">
                <h2> {{ person.name }} </h2>
                <p>craft : <span>{{person.craft}}</span></p>
            </div>
        </div>
        <div v-else>
            Loading
        </div>
        <br>
        <!-- LEARN COMPUTED -->
        <form>
            <label for="product">Name Product: </label>
            <input type="text" id="product" v-model="product">

            <label for="price">Price: </label>
            <input type="number" id="price" v-model="price">

            <label for="discount">Discount: </label>
            <input type="number" id="discount" v-model="discount">

            <label for="number">Number: </label>
            <input type="number" id="number" v-model="number">
        </form>
        <hr>
        <div>
            <p><b> Product: </b><span> {{ product }} </span></p>

            <p><b> First Price: </b><span> {{ price }} </span></p>

            <p><b> Price with discount: </b><span> {{ cost }} </span></p>

            <p><b> Your Price: </b><span> {{ payable }} </span></p>
        </div>
        <br>
        <!--  -->
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
                product : null,
                price : 0,
                discount : 0,
                number : 0
            }
        },
        mounted : function () {
            axios.get('http://api.open-notify.org/astros.json').then(res => this.list = res.data.people);
        },
    }
</script>

<style>

</style>