<template>
  <div id="app">
    <h1>Aplikasi Mengelola Tugas M Hajid Prori Nugraha</h1>
    <div class="input-container">
      <input type="text" v-model="newTask" placeholder="Input data..." />
      <button @click="addTask">Tambah</button>
    </div>
    <ul>
      <li v-for="(task, index) in filteredTasks" :key="index">
        <div class="task-container">
          <span :class="{ 'completed': task.completed }">{{ task.name }}</span>
          <div class="button-container">
            <button @click="toggleTask(index)">
              {{ task.completed ? 'Batal' : 'Selesai' }}
            </button>
            <button @click="removeTask(index)">Remove</button>
          </div>
        </div>
      </li>
    </ul>
    <button @click="showOnlyCompleted = !showOnlyCompleted">
      {{ showOnlyCompleted ? ' < Kembali' : 'Tampilkan Selesai' }}
    </button>
    <footer>
      <p>&copy;MhajidProriNugraha</p>
    </footer>
  </div>
  </template>

<script>
export default {
  data() {
    return {
      newTask: '',
      tasks: [],
      showOnlyCompleted: false
    };
  },
  methods: {
    addTask() {
      if (this.newTask !== '') {
        this.tasks.push({ name: this.newTask, completed: false });
        this.newTask = '';
      }
    },
    removeTask(index) {
      this.tasks.splice(index, 1);
    },
    toggleTask(index) {
      this.tasks[index].completed = !this.tasks[index].completed;
    }
  },
  computed: {
    filteredTasks() {
      if (this.showOnlyCompleted) {
        return this.tasks.filter(task => task.completed);
      } else {
        return this.tasks;
      }
    }
  }
};
</script>

<style scoped>
#app {
  background-color: transparent;
  margin: auto;
  padding: 10px;
  max-width: 500px;
  display: grid;
  justify-items: center;
  align-items: center;
  min-height: 100vh;
}

#app h1 {
  text-align: center;
  margin-left: 10px;
  font-family:monospace;
  font-weight: bold
}

.input-container {
  text-align: center;
  margin-bottom: 10px;
}

#app input[type=text] {
  height: 30px;
  border-radius: 10px;
  font-weight: bold
}

#app button {
  width: 150px;
  height: 35px;
  border-radius: 5px;
  display: inline;
  background-color: darkgrey;
  margin-left: 10px;
  font-family:monospace;
  font-weight: bold;
}

#app button:nth-child(2) {
  width: 70px;
}
#app button:nth-child(1) {
  width: 70px;
}

#app ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

#app li {
  padding: 5px;
  padding-right: -10px;
  display: flex;
  align-items: center;
  color: black;
}
.completed {
  text-decoration: line-through;
  list-style-type: none;
}

.button-container {
  margin-left: auto;
}

.task-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

#app footer > p{
  color: black;
  font-family:monospace;
  font-weight: bold
}
</style>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
