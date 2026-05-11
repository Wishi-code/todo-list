<script>
	export let high = 0;
	export let medium = 0;
	export let low = 0;
	export let personal = 0;
	export let study = 0;
	export let work = 0;

	$: totalTasks = high + medium + low + personal + study + work;
</script>
<main>
    <h2>Total Tasks</h2>
    <p>Keep track of all your tasks in one place!</p>
    <div>
        <p>High : {high}</p>
        <p>Medium : {medium}</p>
        <p>Low : {low}</p>
        <p>Personal: {personal}</p>
        <p>Study : {study}</p>
        <p>Work : {work}</p>
        <h3>Total : {totalTasks}</h3>
    </div>
</main>
<style>
    
</style>