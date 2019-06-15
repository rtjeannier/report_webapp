<template>
  <div class = "container">
    <h1>{{test}}</h1>
    <h2>{{icle}}</h2>
    <button
      v-on:click="runtest()"
      type="button"
      class="btn btn-primary">{{button_text}} times {{count}}</button>

    <form v-on:submit.prevent>
      <div class="test">
        <label for="exampleInputEmail1">Email address</label>
        <input
            v-model="userEmail"
            type="email"
            class="form-control"
            id="exampleInputEmail1"
            aria-describedby="emailHelp"
            placeholder="Enter email">
        <small
          id="emailHelp"
          class="form-text text-muted">This is probably your email: {{userEmail}}</small>
      </div>
    </form>

    <button
      v-on:click="submitEmail()"
      type="button"
      class="btn btn-primary">Click to Submit
    </button>

    <!-- ToDos -->
    <table class="table mt-5">
      <thead>
        <tr>
          <th scope="col">ID</th>
          <th scope="col">Title</th>
          <th scope="col">Completed</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(todo, index) in todos" :key="index">
          <th scope="row">{{todo.id}}</th>
          <td>{{todo.title}}</td>
          <td>{{todo.completed}}</td>
        </tr>
      </tbody>
    </table> 

  </div>
</template>

<script>
export default {
  name: "DataViz",

  data() {
    return {
      test: "My oh my!",
      icle: "Look at that butt",
      button_text: "Butt Stuff",
      count: 0,
      userEmail: '',
      todos: ''
    };
  },

  methods: {
    runtest() {
      console.log("CLICKED!");
      this.count += 1;
    },
    submitEmail(){
        console.log('Email submitted: ', this.userEmail)
    },
    getData(){
        fetch('https://jsonplaceholder.typicode.com/todos')
        .then(response => response.json())
        .then(json => this.todos = json)
    }
  },
  created(){
      this.getData()
  }
};
</script>
