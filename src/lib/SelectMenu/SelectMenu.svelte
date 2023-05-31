<script lang="ts">
	import Select, { Option } from '@smui/select';
	import Icon from '@smui/select/icon';

	export let required: boolean = false;
	export let list: any[] = [];
	export let label: string | undefined = undefined;
	export let disabled: boolean = false;
	export let withLeadingIcon: boolean = false;
	export let icon: string | undefined = undefined;
	export let invalid: boolean = false;

	let value = '';
	let valueInvalid = '';
</script>

<div>
	<Select
		key={(list) => `${list ? list.id : ''}`}
		variant="outlined"
		bind:value
		{required}
		{label}
		{disabled}
		{withLeadingIcon}
		{invalid}
	>
		<svelte:fragment slot="leadingIcon">
			{#if withLeadingIcon}
				<Icon class="material-symbols-outlined">{icon}</Icon>
			{/if}
		</svelte:fragment>
		<Option value="" />
		{#each list as item}
			<Option value={item}>
				{item.label}</Option
			>
		{/each}
	</Select>
</div>
