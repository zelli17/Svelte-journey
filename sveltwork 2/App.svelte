<script>
	let people =[
	{name:'aayush', beltColor:'black', age: 43, id:1},
	{name:'sayush', beltColor:'orange', age: 99, id:2},
	{name:'atyush', beltColor:'green', age: 23, id:3}
	];

	const handleClick = (id) => {
		people = people.filter((person) => person.id != id)
	}
</script>

<main>
	{#each people as person (person.id) }
	<div>
		<h2>{person.name}</h2>
		<h3>{person.beltColor} belt and age is {person.age}</h3>
		<button on:click={() => handleClick(person.id)}>Delete this</button>
	</div>
	{:else}
		<p>no more people remaining</p>
	{/each}
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