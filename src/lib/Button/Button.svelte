<script lang="ts">
	import Button, { Label } from '@smui/button';

	export let label: string | undefined = undefined;

	let className: string = '';
	export { className as class };
</script>

<Button class={className}>
	{#if label}
		<Label>{label}</Label>
	{:else}
		<slot />
	{/if}
</Button>
