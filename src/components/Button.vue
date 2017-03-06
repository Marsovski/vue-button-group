<template>
        <button
            @click="selectBtn"
            :class="{ select: selectClass }"
            type="button"
            ><slot></slot>
        </button>
</template>

<script>
    export default {
        props: ['ides'],
        data: function () {
            return {
                selectClass: false
            }
        },
        methods: {
            selectBtn() {
                // Change class status
                this.selectClass = !this.selectClass;
                // console.log('B: ', this.ides );
                this.$emit('selectButtonEmit', this.ides);
            }
        }
    }
</script>

<style>
    button {
        margin: 20px;
    }

    .select {
        color: red;
    }

    .panel-body {
        font-family: , cursive;
        font-size: 24px;
        color: #6e6e6e;
    }

    .quote {
        cursor: pointer;
    }

    .quote:hover {
        background-color: #ffe2e2;
    }
</style>
