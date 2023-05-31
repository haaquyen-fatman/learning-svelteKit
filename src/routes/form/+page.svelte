<script>
	import Checkbox from '$lib/Checkbox/Checkbox.svelte';
	import TextField from '$lib/Inputs/TextField.svelte';
	import SelectMenu from '$lib/SelectMenu/SelectMenu.svelte';

	let fruits = [
		{ id: 1, label: 'Apple', price: 35 },
		{ id: 2, label: 'Orange', price: 38 },
		{ id: 3, label: 'Banana', price: 28 },
		{ id: 4, label: 'Mango', price: 25 }
	];
</script>

<form>
	<TextField label="Outlined" helperText="demo input" />
	<SelectMenu required list={fruits} label="Fruits" />
	<Checkbox label="Does it work?" />
	<Checkbox label="Does it work?" disabled />
</form>
