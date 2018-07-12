<template>
    <div class="container">
        <app-header :quoteCount="corfinal.length" :maxQuotes="maxQuotes"></app-header>
        <app-new-quote @quoteAdded="newQuote" :corfinal="corfinal"></app-new-quote>
        <app-quote-grid :corfinal="corfinal" @quoteDeleted="deleteQuote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Clique em uma Cor para deletar!</div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import Header from './components/Header.vue';

    export default {
        data: function () {
            return {
                corfinal: [
                    '#06858C',
                    '#45C48B',
                    '#FFD039',
                    '#F47942'
                ],
                maxQuotes: 20
            }
        },
        methods: {
            newQuote(cor1) {
                if (this.corfinal.length >= this.maxQuotes) {
                    return alert('Delete uma cor primeiro!');
                }
                else if (cor1 == '' || cor1[0] != '#') {
                    return alert('Digite uma cor valida usando #');
                }
                else {
                this.corfinal.push(cor1);
                }
            },
            deleteQuote(index) {
                this.corfinal.splice(index, 1);
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header,
        }
    }
</script>

<style>
</style>
