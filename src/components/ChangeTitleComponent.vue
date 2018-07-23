<template>
	<div class="form-group">
		<label>Change the title of your shopping List</label>
		<input @input="onInput({ title: $event.target.value, id: id})" class="form-control" :value="title"/>
	</div>
</template>
<script>
	import { mapActions} from 'vuex'
	export default {
		props: ['value', 'title', 'id'],
		methods: mapActions({
			onInput: 'changeTitle'
		})	
	}
</script>