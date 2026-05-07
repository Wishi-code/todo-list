<script>
    let studyTasks=[
        { task: "Finish math homework", id: 1 },
        { task: "Study for science test", id: 2 },
        { task: "Write history essay", id: 3} 
    ];

    const deleteStudy=(id)=>{
        studyTasks= studyTasks.filter((task)=> task.id != id);
    }
</script>
<main>
    <div>
        <h2>Study Tasks</h2>
        <ul>
            {#each studyTasks as task}
            <div>
                <p>{task.task}</p>
                <button on:click={()=> deleteStudy(task.id)}>Delete Task</button>
            </div>
            {/each}
        </ul>
    </div>
</main>