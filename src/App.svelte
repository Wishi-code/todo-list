<script>
	import High from "./High.svelte";
	import AddTask from "./AddTask.svelte";
	import TaskCount from "./TaskCount.svelte";

// track task arrays  so that taskCount can access them and update the total count when tasks are added or deleted.
	let highPriorityTasks=[
    { task: "Finish the report", id: 1, category: "high" },
    { task: "Prepare for the meeting", id: 2, category: "high" },
    { task: "Respond to urgent emails", id: 3, category: "high" } ,
	
    { task: "Schedule a dentist appointment", id: 6, category: "medium" },
    { task: "Buy groceries", id: 7, category: "medium" },
    { task: "Plan weekend trip", id: 8, category: "medium" } ,

	{ task: "Organize the bookshelf", id: 4, category: "low" },
	{ task: "Water the plants", id: 5, category: "low" },

	{ task: "Call mom", id: 9, category: "personal" },
	{ task: "Go for a run", id: 10, category: "personal" },
	{ task: "Read a book", id: 11, category: "personal" } ,
  
    { task: "Finish math homework", id: 1 , category: "study"},
    { task: "Study for science test", id: 2, category: "study" },
    { task: "Write history essay", id: 3, category: "study" }, 

    { task: "Finish project report", id: 12, category: "work" },
    { task: "Attend team meeting", id: 13, category: "work" },
    { task: "Reply to client emails", id: 14, category: "work" } 
]
 
 const addTask = (task) => {
	const newTask = { ...task }; // create a new task object with a unique id
	highPriorityTasks = [...highPriorityTasks, newTask]; // add the new task to the high priority tasks array
  };

  const deleteTask = (id) => {
	highPriorityTasks = highPriorityTasks.filter((task) => task.id !== id);
  };





	let showHigh = false;
	let showMedium = false;
	let showLow = false;
	let showPersonal = false;
	let showStudy = false;
	let showWork = false;
</script>

	<main>
		<h1>Hello Wishie!</h1>
		<h3>This is my task manager.</h3>
		<p>I have the following tasks to complete: high priority, medium, low, personal, study and work tasks.</p>
		<p>Click on the task to delete it from the list once done.</p>
<div class="task-count">
   
</div>	
		<div>
			<button on:click={() => (showHigh = !showHigh)}>{showHigh ? 'Hide' : 'Show'} High Priority Tasks</button>
			{#if showHigh}
				<High bind:data={highPriorityTasks} category="high" deleteTask={deleteTask} />
			  
			{/if}
		</div>

		<div>
			<button on:click={() => (showMedium = !showMedium)}>{showMedium ? 'Hide' : 'Show'} Medium Priority Tasks</button>
			{#if showMedium}
				<High bind:data={highPriorityTasks} category="medium" deleteTask={deleteTask} />
			{/if}
		</div>

		<div>
			<button on:click={() => (showLow = !showLow)}>{showLow ? 'Hide' : 'Show'} Low Priority Tasks</button>
			{#if showLow}
				<High bind:data={highPriorityTasks} category="low" deleteTask={deleteTask} />
			{/if}
		</div>

		<div>
			<button on:click={() => (showPersonal = !showPersonal)}>{showPersonal ? 'Hide' : 'Show'} Personal Tasks</button>
			{#if showPersonal}
				<High bind:data={highPriorityTasks} category="personal" deleteTask={deleteTask} />
			{/if}
		</div>

		<div>
			<button on:click={() => (showStudy = !showStudy)}>{showStudy ? 'Hide' : 'Show'} Study Tasks</button>
			{#if showStudy}
				<High bind:data={highPriorityTasks} category="study" deleteTask={deleteTask} />
			{/if}
		</div>

		<div>
			<button on:click={() => (showWork = !showWork)}>{showWork ? 'Hide' : 'Show'} Work Tasks</button>
			{#if showWork}
				<High bind:data={highPriorityTasks} category="work" deleteTask={deleteTask} />
			{/if}
		</div>
		<div class="bind">
			<TaskCount
				high={highPriorityTasks.filter((task) => task.category === "high").length}
				medium={highPriorityTasks.filter((task) => task.category === "medium").length}
				low={highPriorityTasks.filter((task) => task.category === "low").length}
				personal={highPriorityTasks.filter((task) => task.category === "personal").length}
				study={highPriorityTasks.filter((task) => task.category === "study").length}
				work={highPriorityTasks.filter((task) => task.category === "work").length}
			/>
		</div>

		
		<AddTask on:add={(data) => { addTask(data.detail)}}/>
	</main>

	<style>
		main {
			min-height: 100vh;
			background-image: linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0.8)), url("https://i.pinimg.com/736x/c4/68/fd/c468fdaaebba505255e9c9cd81a9b702.jpg");
			background-size: cover;
			background-position: center;
			background-repeat: no-repeat;
			text-align: center;
			padding: 1em;
			max-width: 640px;
			margin: 40px auto;
			background-color: white;
			/* gradient applied via background-image above */
		}
		h1 {
			color: darkblue;
			text-decoration: underline wavy;
			font-style: italic;
			font-size: 2em;
		}
		h3 {
			color: darkcyan;
			text-decoration: underline wavy;
			text-transform: capitalize;
			margin: 0.5em;
		}

		h3:hover {
			color: red;
			cursor: pointer;
		}

		button {
			background-color: black;
			color: white;
			border: 2px light cyan solid;
			padding: 0.5em 1em;
			border-radius: 2px;
			cursor: pointer;
			margin: 0.5em;
			
		}

		button:hover {
			background-color: aquamarine;
			color: black;
		}

		p {
			color: black;
			font-size: 1.1em;
		}
	</style>