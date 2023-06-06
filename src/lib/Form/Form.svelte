<svelte:options immutable={true} />

<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	export let defaultValues: any;

	const dispatch = createEventDispatcher();
	function handleSubmitForm() {
		dispatch('submitForm', { defaultValues });
	}
</script>

<form on:submit|preventDefault={handleSubmitForm}>
	<slot />
</form>

<style>
	* :global(.margins) {
		margin: 18px 12px 24px 12px;
	}
	* :global(.columns) {
		display: flex;
		justify-content: space-between;
	}
</style>
