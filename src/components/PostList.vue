<template>
    <div>
        <h3>Список постов</h3>
        <PostItem
            v-for="post in posts"
            :key="post.id"
            :post="post"
        />
    </div>
</template>

<script>
import PostItem from '@/components/PostItem'

    export default {
        components: {
            PostItem
        },

        props: {
            posts: {
                type: Array,
                required: true
            }
        }
    }
</script>

<style scoped>

</style>