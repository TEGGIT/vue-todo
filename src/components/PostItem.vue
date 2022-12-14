<template>
  <div class="post">
    <div>
      <div><strong>Название:</strong>{{post.title}}</div>
      <div><strong>Описание:</strong>{{post.body}}</div>
    </div>
    <div class="post__btns">
      <my-button
          @click="$emit('remove', post)"
          class="button_delete">
        Удалить
      </my-button>
    </div>
  </div>
</template>

<script>

export default {

  props: {
    post: {
      type: Object,
      required: true
    }
  }

}
</script>

<style>

.post {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 15px;
  border: 2px solid green;
  margin-top: 15px;
}

.button_delete {
  border: 1px solid tomato;
}

.button_delete:hover {
  color: white;
  background: tomato;
}

</style>