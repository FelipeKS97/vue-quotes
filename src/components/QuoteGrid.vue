<template>
    <div class="row">
        <app-quote 
            :key="quote" 
            v-for="quote in quotes"
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
    props:['quotes']
}
</script>

<style>

</style>
