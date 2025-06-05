<script lang="ts">
  import Input from "./lib/Input.svelte"
  import Button from "./lib/Button.svelte"

  type Task = {
    title: string
    checked: boolean
  }

  let taskList: Task[] = $state([])

  function addTask(title: string = "Task title") {
    taskList = [...taskList, { title: title, checked: false }]
  }

  function removeTask(i: number) {
    taskList.splice(i, 1)
  }

  addTask("hello");
  addTask("hello");
  addTask("hello");
  addTask("hello");
  addTask("hello");
</script>

<main>
  <div class="tasks-controls">
    <Input name="tasks" placeholder="Enter task" label="Task title" type="text"  />
    <Button text="Add task" onclick={(e: MouseEvent) => {
      console.log("hello!")  
    }}/>
  </div>

  <div class="tasks-container">
    {#each taskList as task (task)}
      <div>
        <p>{task.title}</p>
      </div>
    {/each}
  </div>
</main>

<style>
  @import './shared.css';

  main {
    max-width: 896px;
  }

  .tasks-controls {
    margin-top: 16px;
    display: flex;
    flex-wrap: wrap;
    align-items: last baseline;
    gap: 32px;
  }

  .tasks-container {
    margin-top: 32px;
    display: flex;
    flex-direction: column;
    gap: 16px;
    
    * {
      background-color: var(--color-background-secondary);
    }
  }

</style>
