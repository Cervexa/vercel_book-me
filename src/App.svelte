<script>
	import Navar from './comp/Navar.svelte';
	import NewBooks from './comp/NewBooks.svelte';
</script>

<Navar/>
<main>
	<h1>Nuevos Libros</h1>
	<p>Traemos libros nuevos cada dia para que puedas seguir disfrutando de la lectura</p>	
	<NewBooks/>
</main>

<style>
	*{
		padding: 0;
		margin: 0;
		box-sizing: border-box;
		outline: none;
		border: none;
	}
	main {
		text-align: center;
		max-width: 90%;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
		margin-top: 1rem;
	}

	@media (min-width: 640px) {
		main {
			max-width: 1200px;
		}
	}
</style>