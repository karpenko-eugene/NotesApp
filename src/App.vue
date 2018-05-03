<template>
    <div class="notes-app">
        <h2 class="app-header">NotesApp!</h2>
        <noteEditor />
        <notesGrid :messages="messages" />
    </div>
</template>

<script>
    import noteEditor from './noteEditor.vue'
    import notesGrid from './notesGrid.vue'
    import messages from './data'

    export default {
        components: {
            noteEditor,
            notesGrid
        },

        data() {
            return {
                messages
            }
        }
    }
</script>

<style>
    * {
        box-sizing: border-box;
    }

    body {
        font-family: sans-serif;
        font-weight: 300;
        background-color: #eaeaea;
    }

    .notes-app {
        display: flex;
        flex-direction: column;
        align-items: center;
        max-width: 960px;
        width: 100%;
        margin: 0 auto;
    }

    .app-header {
        text-align: center;
        font-weight: 500;
        color: grey;
        text-shadow: 0px 2px 3px rgba(255,255,255,0.5);
    }
</style>