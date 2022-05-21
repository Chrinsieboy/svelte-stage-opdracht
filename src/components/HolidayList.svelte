<script>
    import { onMount } from "svelte";

    let holidays = [];

    onMount(async () => {
        const response = await fetch(
            "https://holidays.abstractapi.com/v1/?api_key=8d7d830751a5457bb375cab6ad44aa6e&country=NL&year=2020"
        );
        holidays = await response.json();
        console.log(holidays);
    });
</script>

<main>
    <div class="holidays">
        {#each holidays as holiday (holiday)}
            <div class="holiday">
                <p>{holiday.name}</p>
                <ul id="UL">
                    <li>Holiday Type: {holiday.type}</li>
                    <li>Holiday date: {holiday.date}</li>
                    <li>Holiday day of the week: {holiday.week_day}</li>
                </ul>
            </div>
        {/each}
    </div>
</main>

<style>
    .holidays {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
        align-items: left;
        text-align: left;
        /* gap: 1rem; */
    }

    .holiday {
        padding: 5px;
        margin: 10px;
        border: 2px #ff0000 solid;
    }
</style>
