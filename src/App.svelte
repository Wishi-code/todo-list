<script>
	import High from "./high.svelte";
	import Medium from "./medium.svelte";
	import Low from "./low.svelte";
	import Personal from "./personal.svelte";
	import Study from "./study.svelte";
	import Work from "./work.svelte";

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

		<div>
			<button on:click={() => (showHigh = !showHigh)}>{showHigh ? 'Hide' : 'Show'} High Priority Tasks</button>
			{#if showHigh}
				<High />
			{/if}
		</div>

		<div>
			<button on:click={() => (showMedium = !showMedium)}>{showMedium ? 'Hide' : 'Show'} Medium Priority Tasks</button>
			{#if showMedium}
				<Medium />
			{/if}
		</div>

		<div>
			<button on:click={() => (showLow = !showLow)}>{showLow ? 'Hide' : 'Show'} Low Priority Tasks</button>
			{#if showLow}
				<Low />
			{/if}
		</div>

		<div>
			<button on:click={() => (showPersonal = !showPersonal)}>{showPersonal ? 'Hide' : 'Show'} Personal Tasks</button>
			{#if showPersonal}
				<Personal />
			{/if}
		</div>

		<div>
			<button on:click={() => (showStudy = !showStudy)}>{showStudy ? 'Hide' : 'Show'} Study Tasks</button>
			{#if showStudy}
				<Study />
			{/if}
		</div>

		<div>
			<button on:click={() => (showWork = !showWork)}>{showWork ? 'Hide' : 'Show'} Work Tasks</button>
			{#if showWork}
				<Work />
			{/if}
		</div>
	</main>

	<style>
		main {
			background-image: src="https://i.pinimg.com/736x/c4/68/fd/c468fdaaebba505255e9c9cd81a9b702.jpg";
			min-height: 100vh;
			background-image: linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0.8)), url("");
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