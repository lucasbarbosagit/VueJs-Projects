<template>
    <div class="row">
        <app-quote v-for="(corfinal, index) in corfinal" @click.native="deleteQuote(index)" :corfinal="corfinal"></app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue';

    export default {
        props: ['corfinal'],
        components: {
            appQuote: Quote
        },
        methods: {
            deleteQuote(index) {
                this.$emit('quoteDeleted', index);
            }
        }
    }
</script>

<style>
</style>