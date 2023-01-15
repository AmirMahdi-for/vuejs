<template>
    <div>
        {{ message }}
        <br>
        {{ my_data.name }}
        <br>
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
                <tr v-for="person, i in people" :key="person.firstName">
                    <td> {{ i+1 }} </td>
                    <td> {{ person.firstName + ' ' + person.lastName }} </td>
                    <td> {{ person.age }} </td>
                    <td> {{ person.job }} </td>
                </tr>
            </tbody>
        </table>
        <br>
    </div>
</template>

<script>
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
                        firstName : 'Amir',
                        lastName : 'Fakhri',
                        age : '28',
                        job : 'Co-founder'
                    },
                    {
                        firstName : 'Kamand',
                        lastName : 'Soleymani',
                        age : '25',
                        job : 'Manager'
                    },
                    {
                        firstName : 'Nilo',
                        lastName : 'Tahmasb',
                        age : '27',
                        job : 'Developer'
                    },
                ]
            }
        },
    }
</script>

<style>

</style>