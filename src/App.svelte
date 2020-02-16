<script>
	let name = 'Pisia';
	let src = `https://sun9-69.userapi.com/c858028/v858028497/2453f/4WQrwD0FDFA.jpg?ava=1`;
	let htmlString = `<em>Hui</em>`
	let inputValue;
	function handleChange() {
		name = 'changed';
	}

	function submit(event) {		
		console.log(inputValue);
	}
</script>

<main>
	<h1>Hello {name.toUpperCase()}!</h1>	
	<img {src} alt=""/>
	<p>{@html htmlString}</p>
	<button on:click={handleChange}>Change</button>
	<form on:submit|preventDefault|once={submit}>
	<input type="text" on:input={event => (inputValue = event.target.value)}/>
	<button type="submit">Submit</button>
	</form>
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

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>