<template>
  <div>
    <HelloWorld msg="Lista de quehaceres"/>
    <!-- Crea una lista -->
    <input v-model="listName" placeholder="Nombre de la lista">
    <button @click="renameList">Crear Lista</button>
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        {{ task }}
        <button @click="removeTask(index)">Eliminar</button>
        <button @click="modifyTask(index, 'Nombre Nuevo')">Modificar</button>
      </li>
    </ul>
    <!-- Crea y agrega una nueva tarea -->
    <input v-model="newTask" placeholder="Nuevo Quehacer">
    <button @click="addTask">Agregar Tarea</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      listName: '',
      tasks: [],
      newTask: '',
    };
  },
  methods: {
    // Renombra la tarea de la lista
    renameList() {

    },
    // Agrega una tarea de la lista
    addTask() {
      this.tasks.push(this.newTask);
      this.newTask = '';
    },
    // Remueve una tarea de la lista
    removeTask(index) {
      this.tasks.splice(index, 1);
    },
    // Modifica una tarea de la lista
    modifyTask(index, newValue) {
      this.tasks[index] = newValue;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
