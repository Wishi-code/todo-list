<script>
let showMedium = true;
export let mediumPriorityTasks=[
    { task: "Schedule a dentist appointment", id: 6 },
    { task: "Buy groceries", id: 7 },
    { task: "Plan weekend trip", id: 8} 
]
const deleteMedium=(id)=>{
    mediumPriorityTasks= mediumPriorityTasks.filter((task)=> task.id != id);
}
</script>

<main>
    <div>
    {#if showMedium}
        <h2>Medium Priority Tasks</h2>
        <ul>
            {#each mediumPriorityTasks as task}
            <div>
                <p>{task.task}</p>
                <button on:click={()=> deleteMedium(task.id)}>Delete Task</button>
            </div>
            {/each}
        </ul>
    {/if}
         </div>
</main>
<style>

    h2{
        color:darkcyan;
        text-align: center;
        text-decoration: italian;
    }
    p{
        font-weight: bold;
    }  
    button{
        background-color: darkcyan;
        color: white;
        border: 2px light cyan solid;
        padding: 0.5em 1em;
        border-radius: 2px;
        cursor: pointer;
    } 
    button:hover{
        background-color: aquamarine;
        color: black;
    }
    main{
        background-color: black;
        padding: 1em;
        border-radius: 8px;
        margin-bottom: 1em;
    }
    
</style>
