<script lang="ts">
	import Dialog, { Title, Content, Actions } from '@smui/dialog';
	import { Label } from '@smui/button';
	import Button from '$lib/Button/Button.svelte';

	export let btnText: string = 'Dialog';
	export let title: string = '';
	export let content: string = '';
	export let leftBtn: string = 'No';
	export let actionLeft: string | undefined = '';
	export let rightBtn: string = 'Yes';
	export let actionRight: string | undefined = '';

	export let leftBtnDefault: boolean = false;
	export let rightBtnDefault: boolean = false;
	export let open: boolean = false;
	export let response: string = 'Nothing yet.';
	export let closeHandler: (e: CustomEvent<{ action: string }>) => void;
</script>

<Button on:click={() => (open = true)}>
	<Label>{btnText}</Label>
</Button>

<Dialog
	on:SMUIDialog:closed={closeHandler}
	bind:open
	aria-labelledby="simple-title"
	aria-describedby="simple-content"
>
	<Title id="simple-title">{title}</Title>
	<Content id="simple-content">
		{content}
		<slot />
	</Content>
	<Actions>
		{#if actionLeft}
			<Button defaultAction={leftBtnDefault} label={leftBtn} action={actionLeft} />
		{:else}
			<Button defaultAction={leftBtnDefault} label={leftBtn} on:click={() => (open = false)} />
		{/if}
		{#if actionRight}
			<Button defaultAction={rightBtnDefault} label={rightBtn} action={actionRight} />
		{:else}
			<Button defaultAction={rightBtnDefault} label={rightBtn} on:click={() => (open = false)} />
		{/if}
	</Actions>
</Dialog>
