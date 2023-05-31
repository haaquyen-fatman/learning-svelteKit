<script lang="ts">
	import List, { Item, Text } from '@smui/list';
	// @ts-ignore
	import SubItem from './SubItem.svelte';

	export let files: any;
	export let name: string | undefined = undefined;
</script>

<div>
	<List class="demo-list">
		{#if name}
			<Item><Text>{name}</Text></Item>
		{/if}

		{#each files as file}
			{#if file.files}
				<Item wrapper>
					<List class="sub-list">
						<Text>
							<svelte:self {...file} />
						</Text>
					</List>
				</Item>
			{:else}
				<SubItem {...file} />
			{/if}
		{/each}
	</List>
</div>

<style>
	* :global(.demo-list) {
		max-width: 300px;
	}
</style>
