<template>
  <div>
      <div class="aTarea">
          <h4>Crear una nueva tarea</h4>
      </div>
      <form @submit.prevent="agregarTarea">
          <label for="tarea" class="label">Tarea</label>
          <input type="text" v-model="tarea">
          <button type="submit" class="button">Crear</button>
      </form>
      <div v-if="tareas.length > 0">
          <ul>
              <li v-for="(task,index) in tareas" :key="index">{{task}}</li>
          </ul>
      </div>
      
  </div>
</template>

<script>
export default {
    name: "Lista",
    data() {
        return {
            tarea: '',
            tareas: []
        }
    },
    methods: {
        agregarTarea(){
            this.tareas.push(this.tarea);
            this.tarea = '';
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.aTarea {
font-family: Verdana, Geneva, Tahoma, sans-serif;
font-size: 20px;
font-weight: bold;
}
.button {
    margin-left: 10px;
}
.label {
    margin-right: 10px;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
}
</style>
