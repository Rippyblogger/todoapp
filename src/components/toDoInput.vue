<template>
    <div>
      <input type="text" v-model="task" v-on:keyup.enter="addTask" placeholder="Enter task here and press enter">
      <div>
        <div :class="{taskdiv:active}" v-for="(toDo, index) in toDoArray" :key="toDo.array">
          <p :class="{taskcontent:active}">{{toDo.task}}</p>
          <p v-on:click="removeTask(index)" :class="{remove:active}">&times;</p>
        </div>
      </div>
    </div>

    
</template>

<script>
export default {
  name: 'toDoInput',
  data () {
    return {
      task: "",
      id: 4,
      toDoArray:[
        {"id": 1,"task": "Brush my teeth","status": "incomplete"},
        { "id": 2, "task": "Boil some water", "status": "incomplete"},
        { "id": 3, "task": "Make coffee", "status": "incomplete" }
      ],
      active: true
    }
  },
  props: {
    msg: String
  },
  methods:{
    addTask(){ 
      this.toDoArray.push({"id": this.id, "task": this.task, "status": "incomplete"});
      this.task = "";
      this.id++;
    },


    removeTask(index){
      this.toDoArray.splice(index, 1)
    }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.taskdiv{
  display: flex;
  justify-content: space-between;
  padding: 1rem 5rem;
  border-radius: 5px;
  border: 1px solid #1c5ab8;
  margin: 0.5rem;
  font-size: 1.3rem;
}

.taskcontent{
  color: #1c5ab8;
}

.remove{
  cursor: pointer;
  color: #46a6eb;
}

.remove:hover{
  transform: scale(1.5);
}

</style>
