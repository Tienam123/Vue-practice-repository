<script>
import PostList from '@/components/PostList.vue';
import PostForm from '@/components/PostForm.vue';

export default {
  name: 'App',
  components: {
    PostForm, PostList,
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'Javascript', body: 'Javascript универсальный язык прогркамирования 1'},
        {id: 2, title: 'Javascript', body: 'Javascript универсальный язык прогркамирования 2 '},
        {id: 3, title: 'Javascript', body: 'Javascript универсальный язык прогркамирования 3'},
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    },
  },
};
</script>


<template>
  <div class="container">
    <PostForm  @create="createPost"/>
    <PostList
        :posts="posts"

    />

  </div>
</template>


<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  padding: 15px;
}
</style>