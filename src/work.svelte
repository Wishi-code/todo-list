<script>
let showWork = true;
let workTasks=[
    { task: "Finish project report", id: 12 },
    { task: "Attend team meeting", id: 13 },
    { task: "Reply to client emails", id: 14} 
]
const deleteWork=(id)=>{
    workTasks= workTasks.filter((task)=> task.id != id);
}
</script>
<main>
    <div>
        {#if showWork}
            <h2>Work Tasks</h2>
    
        <ul>
            {#each workTasks as task}
            <div>
                <p>{task.task}</p>
                <button on:click={()=> deleteWork(task.id)}>Delete Task</button>
            </div>
            {/each}
        </ul>
        
        {/if}
    </div>
</main>

<style>
    
</style>

