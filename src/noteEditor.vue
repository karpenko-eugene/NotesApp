<template>
    <div class="note-editor">
		<textarea placeholder="Enter your note here..." rows="5" class="textarea" v-model="newMsg" />
        <button class="add-button" :disabled="newMsg.length==0" v-on:click="addMsg()">Add</button>
    </div>
</template>

<script>
	export default {

		data() {
            return {
                newMsg: ""
            }
        },

        methods: {
			addMsg() {
				if (this.newMsg.length!=0) {
					this.$parent.messages.push({
						id: Date.now(),
						text: this.newMsg,
						color: 'yellow'
					});
					this.newMsg = "";
				}
		  	}
        }
	}
</script>

<style>
	.note-editor {
	    width: 100%;
	    max-width: 600px;
	    padding: 16px;
	    margin: 16px auto;
	    background-color: white;
	    box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
	    border-radius: 2px;
	    display: flex;
	    flex-direction: column;
	}

	.textarea {
	    width: 100%;
	    resize: none;
	    margin: 5px;
	    font-size: 14px;
	    border: none;
	    font-weight: 300;
	}

	.textarea:focus {
	    outline: 0;
	}

	.add-button {
	    align-self: flex-end;
	    width: 100px;
	    background-color: #44c767;
	    border-radius: 8px;
	    border: 1px solid #18ab29;
	    cursor: pointer;
	    color: #ffffff;
	    font-size: 14px;
	    padding: 8px 8px;
	    text-transform: uppercase;
	    text-decoration: none;
	    text-shadow: 0px 1px 0px #2f6627;
	}

	.add-button:hover {
	    background-color: #5cbf2a;
	}

	.add-button:active {
	    position: relative;
	    top: 1px;
	}

	.add-button:focus {
	    outline: 0;
	}
</style>