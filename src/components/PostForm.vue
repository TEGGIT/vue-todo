<template>
  <form @submit.prevent>
    <my-input
        v-model="post.title"
        type="text"
        placeholder="Название"/>
    <my-input
        v-model="post.body"
        type="text"
        placeholder="Описание"/>
    <my-button class="btn" @click="createPost">
      Создать
    </my-button>
  </form>
</template>

<script>

import MyInput from "@/components/UI/MyInput";
export default {
  components: {MyInput},
  data() {
    return {
      post: {
        title: '',
        body: '',
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: '',
      }
    }
  }
}
</script>

<style scoped>

form {
  display: flex;
  flex-direction: column;
}

.btn {
  margin-top: 15px;
  border: 1px solid cornflowerblue;
  align-self: flex-end;
}

.btn:hover {
  background: cornflowerblue;
  color: white;
}

</style>