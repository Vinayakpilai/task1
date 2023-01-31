<template>
    <div>
        <h1>{{ message }}</h1>
        <button @click="emitGlobalClickEvent()">Click Me</button>
    </div>
</template>
<script>
import { EventBus } from '../main';

export default {
    name:"ChildComponent",
    props:{
        message: String,
    },
    data(){
        return{
            childMsg:"this message is from child"
        }
    },
    mounted(){
        this.sendMsg();
    },
    methods:{
        sendMsg(){
            this.$emit("child-message", this.childMsg);
        },
        emitGlobalClickEvent(){
            EventBus.$emit('clicked', "This is child to child communication");
        }
    }
}
</script>