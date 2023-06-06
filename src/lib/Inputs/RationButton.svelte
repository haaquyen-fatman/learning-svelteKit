<script lang="ts">
	import Radio from '@smui/radio';
	import FormField from '@smui/form-field';
	export let options: any[] = [];
	export let selected = '';
</script>

<div class="radio-demo">
	{#each options as option}
		<FormField>
			<Radio bind:group={selected} value={option.name} disabled={option.disabled} />
			<span slot="label">
				{option.name}{option.disabled ? ' (disabled)' : ''}
			</span>
		</FormField>
	{/each}
</div>
