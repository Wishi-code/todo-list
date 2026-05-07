<script>
let showLow = true;
    let lowPriorityTasks=[
        { task: "Organize the bookshelf", id: 4 },
        { task: "Water the plants", id: 5 },
    ];

    const deleteLow =(id)=>{
        lowPriorityTasks= lowPriorityTasks.filter((task)=> task.id != id);
    }
</script>

<main>
    <div>
{#if showLow}
        <h2>Low Priority Tasks</h2>
        <ul>
            {#each lowPriorityTasks as task}
            <div>
                <p>{task.task}</p>
                <button on:click={()=> deleteLow(task.id)}>Delete Task</button>
            </div>
            {/each}
        </ul>
        {/if}
    </div>
</main>