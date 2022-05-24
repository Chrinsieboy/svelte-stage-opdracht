<script>
	import HolidayList from "./components/HolidayList.svelte";

	let holidays;


	let searchTerm = "";
	let filterdHolidays = [''];
	
	$: {
		console.log(searchTerm);
	}
</script>

<main>
	<h1>Hello! This is a list of Holidays in 2020</h1>
	<!-- Input field for searching -->
	<input type="text" placeholder="Search for a holiday" bind:value={searchTerm} />
	<HolidayList/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 3em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
