<script lang="ts">
	import Textfield from '@smui/textfield';
	import HelperText from '@smui/textfield/helper-text';
	import Icon from '@smui/textfield/icon';

	export let variant: 'standard' | 'filled' | 'outlined' | undefined = undefined;
	export let label: string | undefined = undefined;
	export let helperText: string | undefined = undefined;

	let value = '';
	let invalid = false;
	$: disabled = !value || invalid;
</script>

<div>
	<Textfield {variant} bind:value {label} withTrailingIcon={!disabled}>
		<svelte:fragment slot="trailingIcon">
			{#if !disabled}
				<Icon class="material-symbols-outlined" role="button">send</Icon>
			{/if}
		</svelte:fragment>
		<HelperText slot="helper">{helperText}</HelperText>
	</Textfield>
</div>
