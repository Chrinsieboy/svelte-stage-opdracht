<script>
    import { onMount } from "svelte";
    
    let holidays = [];

    onMount(async () => {
        const response = await fetch('https://holidays.abstractapi.com/v1/?api_key=8d7d830751a5457bb375cab6ad44aa6e&country=US&year=2020')
        holidays = await response.json()
        console.log(holidays)
    })
</script>

<main>
    {#each holidays as holiday (holiday)}
    <p>{holiday.name}</p>
    <hr>
    {/each}
</main>