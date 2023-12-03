<script>
export default {
  data() {
    return {
      post: {
        title: '',
        body: '',
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now(),
          this.$emit('create', this.post);
      this.post = {
        body:'',
        title:'',
      };

    },

  },
};
</script>

<template>
  <form @submit.prevent>
    <h1>Создание поста</h1>
    <input
        v-model="post.title"
        class="input"
        type="text"
        placeholder="Название поста">
    <input
        v-model="post.body"
        class="input"
        type="text"
        placeholder="Описание поста">
    <button @click="createPost" type="submit">Создать пост</button>
  </form>
</template>

<style lang="scss" scoped>

.input {
  border: 1px solid teal;
  margin-bottom: 10px;
  width: 100%;
  padding: 10px;
}

form {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  button {
    padding: 10px 20px;
    background-color: teal;
    color: aliceblue;
    border: 1px solid teal;

    &:hover {
      background-color: aliceblue;
      color: teal;
    }
  }
}
</style>