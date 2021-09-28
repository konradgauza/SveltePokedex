<script context="module">
	export async function load({page}) {
		const id = page.params.id
		const url = `https://pokeapi.co/api/v2/pokemon/${id}`
		const res = await fetch(url)
		const calledPokemon = await res.json()
		return {
			props: {
				calledPokemon
			}
		}
	}
</script>

<script>
	export let calledPokemon
</script>

<div>
	<h1 class='text-4xl text-center my-8 uppercase'>{calledPokemon.name}</h1>
	<img class="w-40 h-40 m-auto" src={calledPokemon.sprites['front_default']} alt={calledPokemon.name}>
</div>

