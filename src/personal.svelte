<script>
    let persnalTasks=[
        { task: "Call mom", id: 9 },
        { task: "Go for a run", id: 10 },
        { task: "Read a book", id: 11} 
    ];

    const deletePersonal = (id) => {
        persnalTasks = persnalTasks.filter((task) => task.id != id);
    };
</script>

<main>

    <div>
        <h2>Personal Tasks</h2>
        <ul>
            {#each persnalTasks as task}
            <div>
                <p>{task.task}</p>
                <button on:click={()=> deletePersonal(task.id)}>Delete Task</button>
            </div>
            {/each}
        </ul>
    </div>
</main>