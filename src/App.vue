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

        <h1>Demo 1</h1>
        <app-group-button
                :typeArray="false"
                :states="demoOneList"
                :state="demoOneSelect"
                @selectButton="demoOneSelect = $event"
        >
        </app-group-button>
        <hr>
        <pre>{{demoOneSelect}}</pre>

        <h1>Demo 2</h1>
        <app-group-button
                :states="demoTwoList"
                :state="demoTwoSelect"
                @selectButton="demoTwoSelect = $event"
        >
        </app-group-button>
        <hr>
        <pre>{{demoTwoSelect}}</pre>
    </div>
</template>

<script>
    import GroupButton from './components/GroupButton.vue';
    export default {
        name: 'app',
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
                ],
                demoOneSelect: [],
                demoOneList: [
                    {id: 1, name: '1'},
                    {id: 2, name: '2'},
                    {id: 3, name: '3'},
                    {id: 4, name: '4'},
                    {id: 5, name: '5'},
                    {id: 6, name: '6'},
                    {id: 7, name: '7'},
                    {id: 8, name: '8'},
                    {id: 9, name: '9'},
                    {id: 10, name: '10'}
                ],
                demoTwoSelect: [],
                demoTwoList: [
                    1,
                    2,
                    3,
                    4,
                    5,
                    6,
                    7,
                    8,
                    9,
                    10
                ],
            }
        },
        components: {
            appGroupButton: GroupButton
        }
    }
</script>

<style>
    pre {
        height: 200px;
    }
</style>
