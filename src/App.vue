<template>
	<div class="container mt-5">
		<ul class="nav nav-pills mb-3" id="pills-tab" role="tablist">
      <li v-for="(list, index) in shoppinglists" class="nav-item">
        <a class="nav-link" v-bind:class="index===0 ? 'active' : ''" data-toggle="pill" v-bind:href="'#'+list.id" role="tab" v-bind:aria-controls="list.id" aria-selected="true">{{ list.title}}</a>
      </li>
    </ul>
    <div class="tab-content" id="pills-tabContent">
      <div v-for="(list, index) in shoppinglists" class="tab-pane" v-bind:class="index===0 ? ' fade show active': ''" v-bind:id="list.id" role="tabpanel" v-bind:aria-labelledby="list.id">
      	<shopping-lists-component :id="list.id" v-bind:title="list.title" v-bind:items="list.items" @changeTitle="onChangeTitle"></shopping-lists-component>
      </div>
    </div>
	</div>
</template>
<script>
import ShoppingListsComponent from './components/ShoppingListsComponent.vue'
import store from './vuex/store'
import { mapGetters } from 'vuex'
import _ from 'underscore'

export default {
  components: { ShoppingListsComponent },
  computed: mapGetters({
  	shoppinglists: 'getLists'
  }),
  methods: {
  	onChangeTitle (id, text) {
        _.findWhere(this.shoppinglists, {id:id}).title = text
      }
  },
  store
}
</script>
<style></style>