<template>
    <div>
        <p>{{title}}</p>
        <button v-on:click="handleClickCount" > Clicker {{user}}: {{count}}</button>
        <input type="text" v-bind:value="count">
    </div>
        <p>Count: {{count}}</p>
    
</template>
<script>

export default({
    props:['title','user'],
    data(){
        return {
            count: 0
        }
    },
    methods:{
        handleClickCount(){
            console.log(this.count)
            this.count++
            console.log("props",this.user)
            this.$emit('handleClickCount', this.user)
           // this.countJoke()
        },
        countJoke(){
                if(this.count==2){
                    alert("Wow,Magic happened")
                }
        }
    },

})
</script>
<style scoped>

</style>