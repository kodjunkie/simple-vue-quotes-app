<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuote"/>
        <app-new-quote @quotedAdded="newQuote"/>
        <app-quote-grid :quotes="quotes" @quoteDeleted="removeQuote"/>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Info: Click on a Quote to delete it!
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import Header from './components/Header.vue';
    export default {
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header
        },
        data() {
            return {
                quotes: [
                    'Without hard work, nothing grows except weed!',
                ],
                maxQuote: 10
            }
        },
        methods: {
            newQuote(quote) {
                if (this.quotes.length >= this.maxQuote) {
                    return alert("Maximum quotes reached!");
                }
                this.quotes.push(quote);
            },
            removeQuote(index) {
                this.quotes.splice(index, 1);
            }
        }
    }
</script>
