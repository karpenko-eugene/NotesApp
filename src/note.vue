<template>
    <div class="note" :style="{'background-color': bgcolor}">
		<span class="delete-note" @click="deleteNote(index)">x</span>
		<span>{{text}}</span>
    </div>
</template>

<script>
	export default {
		props: ['text', 'bgcolor', 'index'],

		methods: {
			deleteNote(index) {
				this.$parent.$parent.messages.splice(index, 1);
			}
		}
	}
</script>

<style>
	.note {
	    width: 200px;
	    height: auto;
	    float: left;
	    background-color: yellow;
	    box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
	    border-radius: 2px;
	    padding: 10px;
	    margin-bottom: 10px;
	    transition: box-shadow .3s;
	    word-wrap: break-word;
	    position: relative;
	}

	.note:hover {
	    box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
	}

	.delete-note {
	    position: absolute;
	    top:5px;
	    right:5px;
	    display: none;
	    color: rgba(0,0,0,0.6);
	    cursor: pointer;
	}

	.note:hover .delete-note {
	    display: block;
	}
</style>