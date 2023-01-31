<template>
    <div>
        <h1>{{ newMessage }}</h1>
    </div>
</template>
<script>
import { EventBus } from '../main';

export default {
    name:"ChildrenComponent",
    data(){
        return{
            newMessage:""
        }
    },
    mounted(){
        EventBus.$on('clicked', (msg)=>{
            this.newMessage = msg;
        });
    },
}
</script>