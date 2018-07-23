<template>
	<div>
		<item-component v-for="(item, key) in items" :item="item" :key="item.id"></item-component>	
	</div>
</template>
<script>
	import ItemComponent from './ItemComponent'

	export default {
		components: {
			ItemComponent
		},
		props: ['items']
	}
</script>