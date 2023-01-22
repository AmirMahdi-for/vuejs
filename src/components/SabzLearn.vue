<template>
    <div>
        <!-- <p>Counter : {{ counter }}</p>
        <button @click="addCounter"> Add to Counter </button>
        <button @click="minesCounter"> mines to Counter </button><br>
        <a :href="link">ZZZZZZZZ</a>
        <div v-html="title"></div>
        <input type="text" v-model="value">
        <b>{{ value }}</b>
        <br><br>
        <button @click="changeValue()">CHANGE</button>
        <hr>
        <button @click="number++"> Add to Number </button>
        <p>{{ number }}</p>
        <p v-if="number < 10">
            number less than 10
        </p>
        <p v-else>
            number more than 10
        </p>
        <h3 v-show="test">show this TAG</h3>
        <ul v-for="an, i in animals" :key="i">
            <li>{{ i+1 }}. {{ an }}</li>
        </ul>
        <ul v-for="person, i, id in people" :key="i">
            <li>{{id+1}}.{{i}} : {{person}}</li>
        </ul> -->
        <input type="text" v-model="newToDo">
        <button class="btn btn-success sm" @click="addTodo">add TODO</button>
        <ul v-for="x, i in toDo" :key="i">
            <li>
                {{ x }}
                <br>
                <button class="btn btn-danger sm" @click="removeTodo(i)">remove TODO</button>
            </li>
        </ul>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                counter : 0,
                link : "http://google.com",
                title : "<h1>Google</h1>",
                value : "this is new course",
                number : 0,
                test : true,
                animals : ['lion', 'bird', 'elephant', 'tiger'],
                people : {
                    firstName : 'amirMahdi',
                    lastName : 'amiri'
                },
                toDo : ['study', 'goOut', 'coding', 'smoking'],
                newToDo : ''
            }
        },
        methods : {
            addTodo: function(){
                if (this.newToDo == '')  {
                    alert('please add to todo')
                }
                else {
                    this.toDo.push(this.newToDo);
                }
            },
            removeTodo: function(i){
                this.toDo.shift(this.toDo[i])
            },
            addCounter : function() {
                this.counter++;
            },
            minesCounter : function() {
                if(this.counter == 0){
                    alert("can not mines to counter");
                }
                else{
                    this.counter--;
                }
            },
            changeValue: function(){
                this.value = 'Change IT'
            }
        }
    }
</script>
    
<style>

</style>