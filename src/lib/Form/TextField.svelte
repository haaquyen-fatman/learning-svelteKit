<script lang="ts">
	import Textfield from '@smui/textfield';
	import HelperText from '@smui/textfield/helper-text';
	import Icon from '@smui/textfield/icon';

	export let variant: 'standard' | 'filled' | 'outlined' | undefined = undefined;
	export let label: string = '';
	export let helperText: string = '';
	export let invalid: boolean = false;
	export let prefix: string | undefined = undefined;
	export let suffix: string | undefined = undefined;
	export let input$pattern: string | undefined = undefined;
	export let persistent: boolean = false;

	let value = '';
	$: disabled = !value || invalid;
</script>

<div>
	<Textfield
		{variant}
		bind:value
		{label}
		withTrailingIcon={!disabled}
		{invalid}
		{prefix}
		{suffix}
		{input$pattern}
	>
		<svelte:fragment slot="trailingIcon">
			{#if !disabled}
				<Icon class="material-symbols-outlined" role="button">send</Icon>
			{/if}
		</svelte:fragment>
		<HelperText {persistent} slot="helper">{helperText}</HelperText>
	</Textfield>
</div>
