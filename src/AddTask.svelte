<script>
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();
  let newTask = '';
  let category = 'high'; //  declared with default

  const handleSubmit = () => {
    if (newTask.trim()) { //  prevent empty tasks
      dispatch('add', { task: newTask, id: Date.now(), category }); //  auto ID
      newTask = ''; //  clear after submit
    }
  }
</script>

<main>
  <h2>Add a new task</h2>

  <!--  input field added -->
  <input bind:value={newTask} placeholder="Enter task..." />

  <select bind:value={category}>
    <option value="high">High</option>
    <option value="medium">Medium</option>
    <option value="low">Low</option>
    <option value="personal">Personal</option>
    <option value="study">Study</option>
    <option value="work">Work</option>
  </select>

  <!--  matches function name -->
  <button on:click={handleSubmit}>Add Task</button>
</main>