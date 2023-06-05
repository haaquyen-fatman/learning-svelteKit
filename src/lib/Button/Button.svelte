<script lang="ts">
	import Button, { Label } from '@smui/button';

	export let label: string | undefined = undefined;
	export let disabled: boolean = false;
	export let ripple: boolean = true;
	export let touch: boolean = false;
	export let href: string | undefined = undefined;
	export let target: string | undefined = undefined;

	let className: string = '';
	export { className as class };
</script>

<Button class={className} {disabled} {ripple} {touch} {href} {target}>
	{#if label}
		<Label>{label}</Label>
	{:else}
		<slot />
	{/if}
</Button>
