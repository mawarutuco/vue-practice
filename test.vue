const app = Vue.createApp({
    data() {
      return {
        newTodoText: "",
        todos: [
          {
            id: 1,
            title: "Do the dishes",
          },
        ],
        nextTodoId: 2,
      };
    },
    methods: {
      addNewTodo() {
        this.todos.push({
          id: this.nextTodoId++,
          title: this.newTodoText,
        });
        this.newTodoText = "";
      },
    },components:{
      'hyo':{
        template:'123'
      }
    }
  });
  app.component("todo-item", {
    template: `
      <li>
        {{ title }}123456
        <button @click="$emit('remove')">Remove</button>
      </li>
    `,
    props: ["title"],
    emits: ["remove"],
  });
  app.mount("#todo-list-example");