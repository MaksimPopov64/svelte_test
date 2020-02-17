<script>
	let name = 'Pisia';
	let src = `https://sun9-69.userapi.com/c858028/v858028497/2453f/4WQrwD0FDFA.jpg?ava=1`;
	let htmlString = `<em>Hui</em>`
	let inputValue;
	let counter = 0;
	function handleChange() {
		name = 'Changed';
	} 
	
	$: counterClass = counter % 2 === 0 ? 'red' : 'blue';
	$: upperName = name.toUpperCase();
	$: lowerName = name.toLowerCase();

	$: {
		console.log(`${name}`);
	}

	$: {
		if (counter % 10 === 0) {
			counterClass = 'green';
		}
	}

</script>

<main>
	<h1>Hell {upperName}</h1>	
	<h1>ggg {name}</h1>
	<h2>yyy {lowerName}</h2>
	<img {src} alt=""/>
	<p>{@html htmlString}</p>
	<button on:click={handleChange}>Change</button>	
	<h1 class={counterClass}>{counter}</h1>
	<button on:click={() => counter++}>Add</button>
	<input type="text" bind:value={name}/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	:global(p) {
		color: blue;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	img {
		width: 100px;
		border: 1px dotted green;
	}

	.red  {
		color: red;
	}

	.blue {
		color: blue;
	}

	.green {
		color: green;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>