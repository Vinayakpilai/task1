<template>
    <div class="parent-component">
        <ChildComponent :message="message" @child-message="displayMsg"/>
        <ChildrenComponent></ChildrenComponent>
    </div>
</template>
<script>
import ChildComponent from "./Child.vue";
import ChildrenComponent from "./Children.vue";



export default {
    name:"ParentComponent",
    data(){
        return{
            message:"This prop is for child component"
        }
    },
    methods:{
        displayMsg(msg){
            console.log(msg);
        }
    },
    components: {
        ChildComponent,
        ChildrenComponent,
       
    }
}
</script>