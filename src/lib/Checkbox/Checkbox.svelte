<script lang="ts">
	import Checkbox from '@smui/checkbox';
	import FormField from '@smui/form-field';

	export let label: string = 'Checkbox';
	export let disabled: boolean = false;
	let checked = false;
</script>

<FormField>
	<Checkbox bind:checked touch {disabled} />
	<span>{label}</span>
</FormField>

<pre class="status">Checked: {checked}</pre>
