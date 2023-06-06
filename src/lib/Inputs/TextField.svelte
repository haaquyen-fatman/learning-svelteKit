<script lang="ts">
	import Textfield from '@smui/textfield';
	import HelperText from '@smui/textfield/helper-text';

	export let variant: 'standard' | 'filled' | 'outlined' | undefined = undefined;
	export let label: string | undefined = undefined;
	export let required: boolean = false;
	export let helperText: string = '';
	export let invalid: boolean = false;
	export let prefix: string | undefined = undefined;
	export let suffix: string | undefined = undefined;
	export let persistent: boolean = false;
	export let disabled: boolean = false;
	export let textarea: boolean = false;
	export let value: string | number | null | undefined;
	export let type: string = 'text';
</script>

<div>
	<Textfield
		bind:value
		{type}
		{variant}
		{label}
		{required}
		{disabled}
		{invalid}
		{prefix}
		{suffix}
		{textarea}
	>
		<svelte:fragment slot="leadingIcon">
			<slot name="leadingIcon" />
		</svelte:fragment>
		<svelte:fragment slot="trailingIcon">
			<slot name="trailingIcon" />
		</svelte:fragment>

		<HelperText {persistent} slot="helper">{helperText}</HelperText>
	</Textfield>
</div>
