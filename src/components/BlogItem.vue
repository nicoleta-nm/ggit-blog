<template>
    <div>
        <h5>{{ user }}</h5>
        <p>{{ post }}</p>

        <div>
            <button @click="likeItem">Like</button>
            <p>{{ likes }}</p>
            <button @click="dislikeItem">Dislike</button>
            <button @click="deleteItem">Delete</button>
        </div>
    </div>
</template>

<script>
    export default {
        props:{
            id: Number,
            user: String,
            post: String,
            likes: Number,
            tag: String
        },
        emits: ['like','dislike','delete'],
        methods: {
            likeItem() {
               this .$emit("like", {itemId: this.id})
            },
            dislikeItem(){
                this.$emit("dislike", {itemId: this.id})
            },
            deleteItem(){
                this.$emit("delete", {itemId: this.id})
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>