<template>
    <div>
        <div>
            <h4>Crete Post</h4>
            <input
            v-model="post.title"
            class="bg-primary" type="text">
            <input 
            v-model="post.body"
            class="bg-primary" type="text">
            <button @click="createPost" >Create</button>
            </div>


    </div>
</template>
<script>
export default{
    data(){
        return{
            post:{
                title:'',
                body:'',           
             }
        }
    },
    methods:{
        createPost(){
            this.post.id = Date.now()
            this.$emit('create', this.post)
            this.post ={
                title:'',
                body: ''
            }
        }
    }
}
</script>