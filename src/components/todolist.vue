<template>
  <div>
    <div>
      TaskList
    </div>
    <div class="Title">
      状態 名称 締め切り
    </div>
    <div v-for="Task in Tasks" :key="Task.name">
      <div class="Task">
        <div class="Tasks">
          <span v-if="Task.isCompleted == true">完了</span>
          <span v-else>未完了</span>
          {{ Task.name }}
          {{ Task.deadLine }}
          <span v-if="Task.isCompleted == false">
            <button @click="Complete(Task)">完了</button>
          </span>
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
        isCompleted: false,
        name: this.newTaskName,
        deadLine: this.newDeadLine,
      });
    },
    Complete(Task) {
      Task.isCompleted = true;
    },
  },
};
</script>
