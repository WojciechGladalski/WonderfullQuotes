<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" :key="quote.id" @click.native="deleteQuote(index)">{{quote}}</app-quote>
    </div>
</template>

<script>
    import Quote from "@/components/Quote";

    export default {
        name: "QuoteGrid",
        props: ['quotes'],
        components: {
            appQuote: Quote
        },
        methods: {
            deleteQuote(index) {
                this.$emit('quoteDeleted', index)
            }
        }
    }
</script>

<style scoped>

</style>