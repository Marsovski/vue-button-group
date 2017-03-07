<template>
    <div class="row">
        <app-button
            v-for="val in states"
            :ides="val.id"
            :select="bindss(val.id)"
            @selectButtonEmit="selectBtn"
            >
            {{ val.name }}
        </app-button>
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
                required: false,
                default: []
            }
        },
        methods: {
            bindss(ides){
                var st = this.state;
                var status = false;
                st.forEach(function(val) {
                     if (val.id == ides) {
                         status = true;
                     }
                });
                return status;
            },
            selectBtn(ides) {
                var i = 0;
                // states selected
                var st = this.state;

                //
                st.forEach(function(val) {
                    if (val.id == ides) {
                        i++;
                    }
                });


                if (i === 0) {
                    // Add selected
                    st.push({id: ides});
                } else if(i > 0) {
                    // Remove selected
                    st.forEach(function(val, key) {
                        if (val.id == ides) {
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
