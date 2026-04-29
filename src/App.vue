<template>
  <div class="container">
    <h2>To-Do List</h2>

    <!-- Champ de saisie -->
    <input v-model="newTask" type="text" placeholder="Ajouter une tâche" />

    <!-- Bouton ajouter -->
    <button @click="addTask">Ajouter</button>

    <!-- Liste des tâches -->
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        {{ task }}
        <button @click="removeTask(index)">Supprimer</button>
      </li>
    </ul>

    <!-- Bonus -->
    <button @click="clearAll">Tout supprimer</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTask: "",
      tasks: []
    }
  },
  methods: {
    addTask() {
      if (this.newTask.trim() !== "") {
        this.tasks.push(this.newTask)
        this.newTask = "" // vider champ
      }
    },
    removeTask(index) {
      this.tasks.splice(index, 1)
    },
    clearAll() {
      this.tasks = []
    }
  }
}
</script>

<style>
.container {
  text-align: center;
  margin-top: 50px;
}

input {
  padding: 8px;
  margin-right: 10px;
}

button {
  margin-left: 5px;
  padding: 6px;
}

li {
  margin: 10px 0;
}
</style>