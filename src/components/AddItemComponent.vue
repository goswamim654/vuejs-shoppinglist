<template>
	<div>
		<div class="form-group">
			<input type="text" @keyup.enter="addItem" v-model="newItem" class="form-control" placeholder="add shopping list item">
			<button @click="addItem" class="btn btn-primary mt-2 ">Add</button>
		</div>
	</div>
</template>
<script>
	export default {
		data () {
			return {
				newItem: ''
			}
		},
		methods: {
			addItem () {
				var text
				text = this.newItem.trim()
				if(text) {
					this.$emit('add', this.newItem)
					this.newItem = ''
				}
			}
		}
	}
</script>