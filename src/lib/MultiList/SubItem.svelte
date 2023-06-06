<script lang="ts">
	import { Item, Text } from '@smui/list';

	export let name: string;
</script>

<Item on:SMUI:action={() => console.log(name)}>
	<Text>{name}</Text>
</Item>
