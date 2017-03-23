<template>
    <button
            @click="selectBtn"
            class="btn-group"
            :class="{ select: select ? selectClass = select : select }"
            type="button"
    ><slot></slot></button>
</template>

<script>
    export default {
        props: ['ides', 'select'],
        data: function() {
            return {
                selectClass: false
            };
        },
        methods: {
            selectBtn() {
                // Change class status
                this.selectClass = !this.selectClass;
                // console.log('B: ', this.ides );
                this.$emit('selectButtonEmit', this.ides);
            }
        }
    };
</script>

<style>
    button {
        margin: 20px;
    }

    .select {
        color: red;
    }
</style>
