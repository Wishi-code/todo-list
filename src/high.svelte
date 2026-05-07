<script>


// This component displays high priority tasks. It can be used to highlight important tasks that need immediate attention.  
let showHigh = true;
let highPriorityTasks=[
    { task: "Finish the report", id: 1 },
    { task: "Prepare for the meeting", id: 2},
    { task: "Respond to urgent emails", id: 3} 
]
//we want to filter main tasks using their id.
const deleteHigh=(id)=>{
    highPriorityTasks= highPriorityTasks.filter((task)=> task.id != id);
}

</script>


<main>
    {#if showHigh}
        <div class="high">
            <div class="hig">
                <div>
                    <h2>High Priority Tasks</h2>
                    <ul>
                        {#each highPriorityTasks as task}
                            
                                <p>{task.task}</p>
                                <button on:click={() => deleteHigh(task.id)}>Delete Task</button>
                            
                        {/each}
                    </ul>
                </div>
            </div>
        </div>
    {/if}
</main>
<style>
    .high{
        background-color: lightcoral;
        padding: 1em;
        border-radius: 8px;
        margin-bottom: 1em;
    }
    .hig{
        background-color: white;
        padding: 1em;
        border-radius: 8px;
    }
    h2{
        color: darkred;
        text-align: center;
        text-decoration: wavy;
    }
    p{
        font-weight: bold;
    }
</style>