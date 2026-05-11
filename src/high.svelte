<script>

 
export let data =[];
export let category = "high";
//we want to filter main tasks using their id.
export let deleteTask = (id) => {};;

</script>


<main>
    <div class="high">
        <div class="hig">
            <div>
                <h2>High Priority Tasks</h2>
                <ul>
                    {#each data.filter((task) => task.category === category) as task}
                        
                            <p>{task.task}</p>
                            <button on:click={() => deleteTask(task.id)}>Delete Task</button>
                        
                    {/each}
                </ul>
            </div>
        </div>
    </div>
  
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