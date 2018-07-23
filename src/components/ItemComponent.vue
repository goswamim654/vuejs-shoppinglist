<template>
	<li class="list-group-item" :class="{ 'removed' : item.checked }">
		<div class="checkbox">
			<label>
				<input type="checkbox" v-model="item.checked"> <span class="ml-2"> {{ item.text }}</span>
			</label>
		</div>
	</li>
</template>
<script>
	export default {
		props: ['item']
	}
</script>