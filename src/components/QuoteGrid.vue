<template>
    <div class="row">
        <app-quote 
            :key="quote" 
            v-for="(quote, qIndex) in quotes"
            @click.native="deleteQuote(qIndex)"
        >
            {{ quote }}
        </app-quote>
    </div>
    
</template>

<script>
import Quote from './Quote.vue'

export default {
    components: {
        'app-quote': Quote
    },
    props:['quotes'],
    methods: {
        deleteQuote(index) {
            this.$emit('quoteDelete', index)
        }
    }
}
</script>

<style>

</style>
