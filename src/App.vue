<template>
    <div class="container">
        <h1>Object</h1>
        <app-group-button
                :typeArray="false"
                :states="objectList"
                :state="objectSelect"
                @selectButton="objectSelect = $event"
        >
        </app-group-button>
        <hr>
        <pre>{{objectSelect}}</pre>

        <h2>Array</h2>
        <app-group-button
                :typeArray="true"
                :states="arrayList"
                :state="arraySelect"
                @selectButton="arraySelect = $event"
        >
        </app-group-button>
        <hr>
        <pre>{{arraySelect}}</pre>
    </div>
</template>

<script>
    import GroupButton from './components/GroupButton.vue';
    export default {
        data: function () {
            return {
                objectSelect: [{id: 3}, {id: 5}],
                objectList: [
                    {id: 1, name: 'Monday'},
                    {id: 2, name: 'Tuesday'},
                    {id: 3, name: 'Wednesday'},
                    {id: 4, name: 'Thursday'},
                    {id: 5, name: 'Friday'},
                    {id: 6, name: 'Saturday'},
                    {id: 7, name: 'Sunday'}
                ],
                arraySelect: ['Tue', 'Sat'],
                arrayList: [
                    'Mon',
                    'Tue',
                    'Wed',
                    'Thu',
                    'Fri',
                    'Sat',
                    'Sun'
                ]
            }
        },
        components: {
            appGroupButton: GroupButton
        }
    }
</script>

<style>
</style>
