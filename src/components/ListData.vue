<template>
  <div>
    <ol v-if="listTodo.length > 0">
      <li v-for="(todo, index) in listTodo" :key="index">
        <div>
          <div v-if="todo.edit === true">
            <input v-model="todo.text" />
            <button type="button" @click="updateTodo(index)">Update</button>
          </div>
          <div v-else>
            {{ todo.text }}
            <button type="button" @click="editTodo(index)">Edit</button>
            <button type="button" @click="deleteTodo(index)">Hapus</button>
          </div>
        </div>
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  props: {
    listTodo: {
      type: Array,
      required: true,
    },
  },
  methods: {
    deleteTodo(index) {
      this.$emit("deleteTodo", index);
    },
    editTodo(index) {
      this.$emit("editTodo", index);
    },
    updateTodo(index) {
      this.$emit("updateTodo", index);
    },
  },
};
</script>
