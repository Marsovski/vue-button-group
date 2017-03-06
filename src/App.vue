<template>
    <div class="container">
        <app-group-button
            :states="weeks"
            @selectButton="selectBtn"
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
                week: [],
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
        methods: {
            selectBtn(index) {
                this.week = index;
                console.log('state ', index);
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
