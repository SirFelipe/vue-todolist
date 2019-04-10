<template>
    <div class="container">
        <div class="col-md-12">
            <p></p>
            <input type="text" v-model="txt" v-on:change="enter"/>
        </div>
    </div>
    
</template>

<script>
export default {
    data(){
       return { txt: "" }
    },methods:{
        enter(){
            this.$emit("mudou", this.txt);
        }
    }
}
</script>

<style scoped>
    
</style>
