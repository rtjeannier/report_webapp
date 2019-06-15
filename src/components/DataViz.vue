<template>
  <div class = "container">
    <h1>{{test}}</h1>
    <h2>{{icle}}</h2>
    <button
      v-on:click="runtest()"
      type="button"
      class="btn btn-primary"
    >{{button_text}} times {{count}}</button>

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
      userEmail: ''
    };
  },

  methods: {
    runtest() {
      console.log("CLICKED!");
      this.count += 1;
    }
  }
};
</script>
