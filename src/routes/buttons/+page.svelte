<script lang="ts">
	import Button from '$lib/Button/Button.svelte';
</script>

<div>
	<div class="mdc-typography--headline4">Demo Button</div>
	<Button class="btn" label="Testing" />
	<Button disabled>Disabled</Button>
	<Button ripple={false}>No Ripple</Button>
	<Button touch={true}>Touch</Button>
	<Button href="http://example.com" target="_blank" label="Link" />
	<Button>no content</Button>
</div>

<style>
	* :global(.btn) {
		font-style: italic;
		background-color: yellow;
		color: white;
	}
</style>
