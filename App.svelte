<script>
	let firstname = "jimmy";
	let lastname = 'hendrix';
	let beltcolor = 'black';

	$: fullname = `${firstname} ${lastname}`;
	$: console.log(beltcolor)
	
	const handleclick = () => {
		beltcolor = 'orange';
	};

	const handleip = (e) =>{
		beltcolor = e.target.value;
	};
</script>

<main>
	<h1>Hello {name}!</h1>
	<p >{fullname} - {beltcolor}belt</p>
	<button on:click={handleclick}>update button color</button>
	<!-- <input type="text" on:input={handleip} value={beltcolor}/> -->

	<input type="text" bind:value={firstname}/>
	<input type="text" bind:value={lastname}/>
	<input type="text" bind:value={beltcolor}/>

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
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>