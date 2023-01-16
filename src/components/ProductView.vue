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
    </div>
</template>

<script>
    import axios from 'axios';
    export default {
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
            }
        },
        mounted : function () {
            axios.get('http://api.open-notify.org/astros.json').then(res => this.list = res.data.people);
        },
    }
</script>

<style>

</style>