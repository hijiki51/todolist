<template>
  <div>
    <div>
      TaskList
    </div>
    <div class="Task">
      <div class="Title">
        状態 名称 締め切り
      </div>
      <div v-for="Task in Tasks" :key="Task.name">
        <div class="Tasks">
          {{ Task.isCompleted }}
          {{ Task.name }}
          {{ Task.deadLine }}
        </div>
      </div>
    </div>
    <div>
      <label>
        名称
        <input type="text" v-model="newTaskName" />
      </label>
      <label>
        期限
        <input type="date" v-model="newDeadLine" />
      </label>
      <button @click="addTask">追加</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TaskList",
  data() {
    return {
      Tasks: [],
      newTaskname: "",
      newTaskDeadLine: "",
    };
  },
  methods: {
    addTask() {
      this.Tasks.push({
        isCompleted: "未完了",
        name: this.newTaskName,
        deadLine: this.newDeadLine,
      });
    },
  },
};
</script>
