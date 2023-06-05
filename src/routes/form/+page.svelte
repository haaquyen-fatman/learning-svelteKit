<script>
	import Checkbox from '$lib/Form/Checkbox.svelte';
	import TextField from '$lib/Form/TextField.svelte';
	import SelectMenu from '$lib/Form/SelectMenu.svelte';

	let fruits = [
		{ id: 1, label: 'Apple', price: 35 },
		{ id: 2, label: 'Orange', price: 38 },
		{ id: 3, label: 'Banana', price: 28 },
		{ id: 4, label: 'Mango', price: 25 }
	];
</script>

<form>
	<TextField label="Outlined" helperText="demo input" />
	<TextField label="Outlined" />

	<SelectMenu required list={fruits} label="Fruits" />
	<Checkbox label="Does it work?" />
	<Checkbox label="Does it work?" disabled />
</form>
