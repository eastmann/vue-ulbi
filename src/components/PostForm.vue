<template>
    <form @submit.prevent>
        <h4>Создание поста</h4>
        <input
            class="input"
            type="text"
            placeholder="Название"
            v-model="post.title"
        >
        <input
            class="input"
            type="text"
            placeholder="Описание"
            v-model="post.body"
        >
        <MyButton @click="createPost">Создать</MyButton>
    </form>
</template>

<script>
export default {
    data() {
        return {
            post: {
                title: '',
                body: ''
            }
        };
    },

    methods: {
        createPost() {
            this.post.id = Date.now();
            this.$emit('create', this.post);
            this.post = {
                title: '',
                body: ''
            };
        }
    },
}
</script>

<style scoped>
form {
    display: flex;
    flex-direction: column;

}
form .btn {
    align-self: flex-end;

    margin-top: 15px;
}

.input {
    margin-top: 15px;
    padding: 10px 15px;

    width: 100%;

    border: 1px solid teal;
}
</style>