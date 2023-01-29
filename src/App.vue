<template>
    <div class="app">
        <form>
            <h4>Создание поста</h4>
            <input class="input" type="text" placeholder="Название">
            <input class="input" type="text" placeholder="Описание">
            <button class="btn"
                    @click.prevent="createPost">Создать</button>
        </form>
        <div class="post"
             v-for="post in posts"
             :key="post.id">
             <div><strong>Название: </strong>{{ post.title }}</div>
            <div><strong>Описание: </strong>{{ post.body }}</div>
        </div>


    </div>
</template>

<script>
export default {
    data() {
        return {
            posts: [
                { id: 1, title: 'JavaScript', body: 'Описание поста'},
                { id: 2, title: 'JavaScript 2', body: 'Описание поста 2'},
                { id: 3, title: 'JavaScript 3', body: 'Описание поста 3'},
            ]
        }
    },

    methods: {
        createPost() {
            console.log('Post created')
        }
    }
}
</script>

<style>
* {
    margin: 0;
    padding: 0;

    box-sizing: border-box;
}

form {
    display: flex;
    flex-direction: column;
}

.app {
    padding: 20px;
}

.post {
    margin-top: 15px;
    padding: 15px;

    border: 2px solid teal;
}

.input {
    margin: 15px;
    padding: 10px 15px;

    width: 100%;

    border: 1px solid teal;
}

.btn {
    align-self: flex-end;

    padding: 10px 15px;
    margin-top: 15px;

    color: teal;

    background: none;
    border: 1px solid teal;
    cursor: pointer;
}
</style>