<script lang="ts">
	import Checkbox from '$lib/Inputs/Checkbox.svelte';
	import TextField from '$lib/Inputs/TextField.svelte';
	import SelectMenu from '$lib/Inputs/SelectMenu.svelte';
	import Button from '$lib/Button/Button.svelte';
	import Icon from '@smui/textfield/icon';
	import Form from '$lib/Form/Form.svelte';
	import RationButton from '$lib/Inputs/RationButton.svelte';

	let fruits = [
		{ id: 1, label: 'Apple', price: 35 },
		{ id: 2, label: 'Orange', price: 38 },
		{ id: 3, label: 'Banana', price: 28 },
		{ id: 4, label: 'Mango', price: 25 }
	];

	let options = [
		{
			name: 'Bashful',
			disabled: false
		},
		{
			name: 'Doc',
			disabled: true
		},
		{
			name: 'Dopey',
			disabled: false
		},
		{
			name: 'Happy',
			disabled: false
		},
		{
			name: 'Sleepy',
			disabled: false
		},
		{
			name: 'Sneezy',
			disabled: false
		},
		{
			name: 'Grumpy',
			disabled: false
		}
	];

	let defaultValues = {
		valueA: '',
		valueB: '',
		valueC: '',
		valueD: '',
		valueE: '',
		valueF: '',
		valueG: '',
		valueH: false,
		valueI: ''
	};
	let values: any = [];

	function clearInput() {
		defaultValues = {
			valueA: '',
			valueB: '',
			valueC: '',
			valueD: '',
			valueE: '',
			valueF: '',
			valueG: '',
			valueH: false,
			valueI: ''
		};
	}

	function handleSubmitForm() {
		values = [
			...values,
			{
				valueA: defaultValues.valueA,
				valueB: defaultValues.valueB,
				valueC: defaultValues.valueC,
				valueD: defaultValues.valueD,
				valueE: defaultValues.valueE,
				valueF: defaultValues.valueF,
				valueG: defaultValues.valueG,
				valueH: defaultValues.valueH,
				valueI: defaultValues.valueI
			}
		];
		console.log(values);
		clearInput();
	}
</script>

<Form {defaultValues} on:submitForm={handleSubmitForm}>
	<div class="columns margins">
		<TextField bind:value={defaultValues.valueA} />
		<TextField
			bind:value={defaultValues.valueB}
			label="Standard with help text"
			helperText="demo input"
		/>
		<TextField
			bind:value={defaultValues.valueC}
			label="Outlined without help text"
			variant="outlined"
		/>
	</div>
	<div class="columns margins">
		<TextField
			bind:value={defaultValues.valueD}
			label="Filled with required"
			variant="filled"
			required
		/>

		<TextField bind:value={defaultValues.valueE} label="icon">
			<Icon class="material-symbols-outlined" role="button" slot="trailingIcon">send</Icon>
		</TextField>
		<TextField bind:value={defaultValues.valueF} label="Prefixed" variant="outlined" prefix="$" />
	</div>
	<SelectMenu bind:value={defaultValues.valueG} required list={fruits} label="Fruits" />
	<Checkbox label="Does it work?" bind:checked={defaultValues.valueH} />
	<Checkbox label="Does it work?" disabled />
	<RationButton {options} bind:selected={defaultValues.valueI} />
	<Button class="btn" label="Submit" type="Submit" />
</Form>
