<template>
  <div class="home">
    <div id="header">
      <img alt="Vue logo" src="../assets/logo.png" width="30" height="30">
      <h2>Vue Trello</h2>
    </div>
    <div id="main">
      <h2>boards</h2>
      <p>sample text</p>
      <div class="board todo">
        <h3>Todo</h3>
        <draggable v-model="tasks">
          <div class="task" v-for="(v, i) in tasks" :key="i"> {{ v }} </div>
        </draggable>
        <div class="append-task">+</div>
      </div>
      <div class="board doing">
        <h3>Doing</h3>
        <draggable v-model="tasks">
          <div class="task" v-for="(v, i) in tasks" :key="i"> {{ v }} </div>
        </draggable>
        <div class="append-task">+</div>
      </div>
      <div class="board done">
        <h3>Done</h3>
        <draggable v-model="tasks">
          <div class="task" v-for="(v, i) in tasks" :key="i"> {{ v }} </div>
        </draggable>
        <div class="append-task">+</div>
      </div>
      <div class="board append-card">
        <h3>+</h3>
      </div>
    </div>
  </div>
</template>

<script>
import draggable from 'vuedraggable'

export default {
  name: 'Home',
  components: {
    draggable,
  },
  data() {
    return {
      tasks: [
        "task1",
        "task2",
        "task3"
      ],
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#header {
  background: teal;
  display: flex;
  padding: 10px 0;
}
#header > img {
  margin: auto 10px;
}
#header > p {
  margin: auto 0;
}
#main {
  margin: 10px 30px;
}
h3 {
  padding: 20px 10px;
  border-bottom: 1px solid silver;
}
ul {
  list-style-type: none;
  padding: 0;
}
.task {
  height: 60px;
  margin: 5px 10px;
  background: white;
  border-radius: 2px;
  box-shadow: 2px 2px 2px;
}
a {
  color: #42b983;
}
.board {
  width: 200px;
  display: inline-block;
  vertical-align: top;
  background: rgb(221, 221, 221);
  margin: 5px 2px;
  border-radius: 2px;
  color: dimgray;
}
.append-card {
  text-align: center;
}
.append-task {
  text-align: center;
  margin: 10px 2px;
}
</style>
