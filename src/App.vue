<template>
    <div class="container">
        <app-group-button
            :states="weeks"
            :state="week"
            @selectButton="week = $event"
            >
        </app-group-button>

        <hr>
        <pre>{{week}}</pre>
    </div>
</template>

<script>
    import GroupButton from './components/GroupButton.vue';
    import Button from './components/Button.vue';

    export default {
        data: function () {
            return {
                week: [{id: 3}, {id: 5}],
                weeks: [
                    {id: 1, name: 'Monday'},
                    {id: 2, name: 'Tuesday'},
                    {id: 3, name: 'Wednesday'},
                    {id: 4, name: 'Thursday'},
                    {id: 5, name: 'Friday'},
                    {id: 6, name: 'Saturday'},
                    {id: 7, name: 'Sunday'}
                ]
            }
        },
        components: {
            appGroupButton: GroupButton,
            appButton: Button
        }
    }
</script>

<style>
</style>
