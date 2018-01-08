<template>
    <div>
        <input type="text" v-model="title"><br />
        <h1>{{title}}</h1>
        <p v-html="titlewithhtml"></p>
        <p v-if="showName">{{user.firstName}} {{user.lastName}}</p>
        <p v-else>Nobody</p>
        <p>
            <span v-text="user.firstName"></span>
            <span v-text="user.lastName"></span>
        </p>
        <ul>
            <li v-for="item in items">{{item.title}}</li>
        </ul>
        <button v-on:click="greet('Hello World!')">Greeting</button>
        <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit" >
        <hr />
        <label>First name     </label><input type="text" v-model="user.firstName">
        <br /> 
        <label>Last name  </label><input type="text" v-model="user.lastName">
        <br />
        <h3>{{fullName}}</h3>
        <h2>{{msg}}</h2>
    </div>
</template>
<!--<script lang="ts"> using tyepscript later-->
<script>
    export default {
        name:'test',
        props:{
            msg:{
                type: String,
                default:'Foobar' 
            }
        },
        data() {
            return {
                title: "hello world",
                titlewithhtml:"<h4>hello world</h4>",
                user:{
                    firstName:'John',
                    lastName:'Doe'
                },
                showName: false,
                items:[
                    {title:'item one'},
                    {title:'item two'},
                    {title:'item three'}
                ]
            }
        },
        methods: {
            greet: function(greeting){
                alert(greeting);
            },
            pressKey: function(e){
                console.log(e.target.value);

            },
            enterHit: function(e){
                console.log('Enter hit '+e.target.value);
            }
        },
        computed:{
            fullName: function(){
                return this.user.firstName + ' '+ this.user.lastName;
            }
        }
    }
</script>

<<style scoped>
    
</style>
