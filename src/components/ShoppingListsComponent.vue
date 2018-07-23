<template>
  <div id="app" class="container mt-5">
    <h2>{{title}}</h2>
    <hr>
    <add-item-component v-on:add="addItem"></add-item-component>
    <hr>
    <h3>Shopping Items:</h3>
    <items-component :items="items"></items-component>
    <hr>
    <div class="footer">
      <change-title-component @changeTitle="onChangeTitle" :id="id"></change-title-component></div>
  </div>
</template>

<script>
  import AddItemComponent from './AddItemComponent'
  import ItemsComponent from './ItemsComponent'
  import ChangeTitleComponent from './ChangeTitleComponent'

  export default {
    components: {
      AddItemComponent,
      ItemsComponent,
      ChangeTitleComponent      
    },
    props: ['id','title', 'items'],
    methods: {
      addItem (text) {
        this.items.push({
          text: text,
          checked: false
        })
      }, onChangeTitle (text) {
        this.$emit('changeTitle', this.id, text )
      }
    }
  }
</script>

<style>

</style>
