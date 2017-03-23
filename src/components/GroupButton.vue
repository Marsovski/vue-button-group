<template>
    <div class="row">
        <app-button
                v-for="val in states"
                :key="val.id || val"
                :ides="val.id || val"
                :select="bindss(val.id || val)"
                @selectButtonEmit="selectBtn"
                >{{ val.name || val }}</app-button>
    </div>
</template>

<script>
    import Button from './Button.vue';
    export default {
        props: {
            states: {
                type: [Object, Array],
                required: true
                // ,
                // validator: function(val) {
                //     return val.length > 0;
                // }
            },
            state: {
                type: [Object, Array],
                required: false
            },
            typeArray: {
                type: Boolean,
                default: true,
                required: false
            }
        },
        methods: {
            bindss(ides) {
                // Props
                let propTypeArray = this.typeArray;
                let propState = this.state;

                // Params
                let status = false;


                /**
                 * Array data
                 */
                if (propTypeArray) {
                    propState.forEach(function (val) {
                        if (val === ides)
                            status = true;
                    });
                }

                /**
                 * Object data
                 */
                if (!propTypeArray) {
                    propState.forEach(function (val) {
                        if (val.id === ides)
                            status = true;

                    });
                }
                return status;
            },
            selectBtn(ides) {
                // Props
                // states selected
                let propTypeArray = this.typeArray;
                let propState = this.state;

                // Params
                let i = 0;

                /**
                 * Array data
                 */
                if (propTypeArray) {
                    propState.forEach(function (val) {
                        if (val === ides)
                            i++;
                    });
                }

                /**
                 * Object data
                 */
                if (!propTypeArray) {
                    propState.forEach(function (val) {
                        if (val.id === ides)
                            i++;
                    });
                }


                if (i === 0 && !propTypeArray) {
                    // Add selected
                    /**
                     * Object data
                     */
                    propState.push({id: ides});
                }
                else if (i === 0 && propTypeArray) {
                    /**
                     * Array data
                     */
                    propState.push(ides);
                }
                else if (i > 0 && !propTypeArray) {
                    // Remove selected
                    propState.forEach(function (val, key) {
                        if (val.id === ides)
                            propState.splice(key, 1);
                    });
                }
                else if (i > 0 && propTypeArray) {
                    // Remove selected
                    propState.forEach(function (val, key) {
                        if (val === ides)
                            propState.splice(key, 1);
                    });
                }

                // console.log('GB ', ides);

                // Emit Event
                this.$emit('selectButton', propState);
            }
        },
        components: {
            appButton: Button
        }
    };
</script>

<style>
</style>
