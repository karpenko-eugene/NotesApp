<template>
    <div item-selector=".note" class="notes-grid" ref="grid" >
		<note v-for="(message, index) in messages" :key="message.id" :text="message.text" :bgcolor="message.color" :index="index" />
    </div>
</template>

<script>
	import note from './note.vue'
	import Masonry from 'masonry-layout'

	export default {
		components: {
            note
        },

		props: ['messages'],

		mounted() {
			var grid = this.$refs.grid;
	        this.msnry = new Masonry(grid, {
	            itemSelector: '.note',
	            columnWidth: 200,
	            gutter: 10,
	            isFitWidth: true
	        });
		},

		updated() {
	        this.msnry.reloadItems();
            this.msnry.layout();
		}
	}
</script>

<style>
	.notes-grid {
	    margin: 0 auto;
	}
</style>