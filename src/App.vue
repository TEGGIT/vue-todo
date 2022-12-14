<template>
  <div class="app">
  <post-form  @create="createPost" />
   <post-list
       @remove="removePost"
       :posts="posts"
   />
  </div>
</template>

<script>

import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";

export default {

  components: {
    PostList, PostForm
  },
  data() {
    return {
      posts: [
        {id: 1, title: '123', body: 'booody'},
        {id: 2, title: '6', body: 'boood43y2'},
        {id: 3, title: '9', body: 'boo23ody3'},
        {id: 4, title: '10', body: 'boo23od22y3'},
      ],
    }
  },
  methods: {
    createPost(post) {
     this.posts.push(post)
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
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

.app {
  padding: 20px;
}

</style>
