<template>
    <div class="row">
        <app-button
            v-for="state in states"
            :ides="state.id"
            @selectButtonEmit="selectBtn"
            >
            {{ state.name }}
        </app-button>
    </div>
</template>

<script>
    import Button from './Button.vue';

    export default {
        props: {
            states: {
                type: [Object, Array]
                // required: true,
                // validator: function(val) {
                //     return val.length > 0;
                // }
            }
        },
        data: function () {
            return {
                state: []
            }
        },
        methods: {
            selectBtn(ides) {
                var i = 0;
                // states selected
                var st = this.state;

                //
                st.forEach(function(val) {
                    if (val == ides) {
                        i++;
                    }
                });


                if (i === 0) {
                    // Add selected
                    st.push(ides);
                } else if(i > 0) {
                    // Remove selected
                    st.forEach(function(val, key) {
                        if (val == ides) {
                            st.splice(key, 1);
                        }
                    });
                }

                // console.log('GB ', ides);

                // Emit Event
                this.$emit('selectButton', st);
            }
        },
        components: {
            appButton: Button
        }
    }
</script>

<style>

</style>
