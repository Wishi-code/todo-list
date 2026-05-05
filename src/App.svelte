<script>
	let name = "Wishie";
	let mainTasks = [
		{ task: "Buy milk", id: 1 },
		{ task: "Clean the house", id: 2 },
		{ task: "Pay bills", id: 3 },
		{ task: "Finish the project", id: 4 },
		{ task: "Walk the dog", id: 5 },
		{ task: "Finish the report", id: 6 }
	];
	let extraTasks = [ { activity: "Learn Svelte", id: 7 }, 
	{ activity: "Go for a run", id: 8 }, 
	{ activity: "Call a friend", id: 9 } ];

	const deleteMain = (id) => {
		mainTasks = mainTasks.filter((task) => task.id != id);
	};
	const deleteExtra=(id)=>{
		extraTasks= extraTasks.filter((activity)=>activity.id !=id);
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<h3>This is my to-do list</h3>
	<h2>Main Tasks:</h2>
	<ul>
		{#each mainTasks as task}
		<div>
		<p>{task.task}</p>
         <button on:click={() => deleteMain(task.id)}>Delete Task</button>
		</div>
		{/each}
	</ul>
	


	<h3>If I have extra time, I will work on the following:</h3>
	<ul>
		{#each extraTasks as activity}
		<div>
			<p>{activity.activity}</p>
			 <button on:click={() => deleteExtra(activity.id)}>Delete Activity</button>
		</div>
		{/each}
	</ul>
</main>

<style>
h3{
	color:darkgoldenrod;
	text-align: center;
	text-decoration: wavy;
	text-transform: capitalize;
	letter-spacing: 0cap;
	margin: 0.5em;
	
}
h3:hover{
	color:red;
	cursor:pointer;
}

body{
	background-color: #121212;
	color: #e0e0e0;
	display: flex;
	align-items: center;
	scroll-behavior: smooth;

	font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
button{
	background-color: #ff3e00;
	color: white;
	border: none;
	padding: 0.5em 1em;
	border-radius: 4px;
	cursor: pointer;
	margin-left: 1em;
}
.button:hover{
	background-color:aquamarine;
	color: black;}
	p{
		color: black
		font-size: 1.2em;
		
	}
	/*main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}*/

</style>