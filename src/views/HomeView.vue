<template>
  <div class="wrapper">
    <TodoListComponent :todoList="todoList" />
    <footer class="footer">© {{ new Date().getFullYear() }}.  Author Name</footer>
  </div>
</template>

<script>
import TodoListComponent from "@/components/TodoListComponent";

export default {
  name: 'HomeView',
  data() {
    return {
      todoList: [
        {
          listItemText: 'delectus aut autem',
          listItemSubtext: 'laboriosam mollitia et enim quasi adipisci quia provident illum',
        },

        {
          listItemText: 'quo laboriosam deleniti aut qui',
          listItemSubtext: '',
        },
        {
          listItemText: 'laboriosam mollitia et enim quasi adipisci quia provident illum',
          listItemSubtext: '',
        },
        {
          listItemText: 'repellendus sunt dolores architecto voluptatum',
          listItemSubtext: 'accusamus eos facilis sint et aut voluptatem',
        },
        {
          listItemText: 'delectus aut autem',
          listItemSubtext: 'laboriosam mollitia et enim quasi adipisci quia provident illum',
        },

        {
          listItemText: 'quo laboriosam deleniti aut qui',
          listItemSubtext: '',
        },
        {
          listItemText: 'laboriosam mollitia et enim quasi adipisci quia provident illum',
          listItemSubtext: '',
        },
        {
          listItemText: 'repellendus sunt dolores architecto voluptatum',
          listItemSubtext: 'accusamus eos facilis sint et aut voluptatem',
        },
        {
          listItemText: 'delectus aut autem',
          listItemSubtext: 'laboriosam mollitia et enim quasi adipisci quia provident illum',
        },
        {
          listItemText: 'delectus aut autem',
          listItemSubtext: 'laboriosam mollitia et enim quasi adipisci quia provident illum',
        },
        {
          listItemText: 'delectus aut autem',
          listItemSubtext: 'laboriosam mollitia et enim quasi adipisci quia provident illum',
        },
        {
          listItemText: 'delectus aut autem',
          listItemSubtext: 'laboriosam mollitia et enim quasi adipisci quia provident illum',
        },

        {
          listItemText: 'quo laboriosam deleniti aut qui',
          listItemSubtext: '',
        },
        {
          listItemText: 'laboriosam mollitia et enim quasi adipisci quia provident illum',
          listItemSubtext: '',
        },
        {
          listItemText: 'repellendus sunt dolores architecto voluptatum',
          listItemSubtext: 'accusamus eos facilis sint et aut voluptatem',
        }
      ]
    }
  },
  components: {
    TodoListComponent,
  },
}
</script>
<style scoped lang="scss">
.wrapper {
  max-width: 420px;
  width: 100%;
  height: 540px;
  @media (max-width: 768px) {
    margin-top: 100px;
  }
}

.footer {
  padding: 30px 0;
}
</style>
