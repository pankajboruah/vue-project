<template>
    <div class="container">
        <app-header :maxCount="maxQuotes" :quoteCount="quotes.length"/>
        <app-new-quote @addQuote="addNewQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a quote to delete it!</div>
            </div>
        </div>
    </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue'
import NewQuote from './components/NewQuote.vue'
import Header from './components/Header.vue'
    export default {
        data:function(){
            return{
                quotes:[
                    'A happy quote'
                ],
                maxQuotes: 10
            }
        },
        components:{
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header
        },
        methods:{
            addNewQuote(quote){
                if(this.quotes.length >= this.maxQuotes){
                    return alert('Please delete some quotes first!')
                }
                this.quotes.push(quote);
            },
            deleteQuote(i){
                this.quotes.splice(i,1);
            }
        }
    }
</script>

<style>
</style>
