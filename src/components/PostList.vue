<template>
<div>

    <div v-for="post in posts" :key="post" class="text-center">
        <div class="mt-[30px]"><strong>Name of post:</strong> {{ post.title }} </div>
        <div><strong>Description:</strong> {{ post.body }} </div>
        </div>














</div>


</template>
<script>

export default{
    props:{
        posts:{
            type:Array,
            required: true
        }
    }
}
</script>