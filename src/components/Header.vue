<template>
    <div class="row">
        <div class="col-sm-12">
            <h3>Quotes Progress</h3>
            <div class="progress">
                <div 
                    class="progress-bar" 
                    role="progressbar" 
                    aria-valuenow="60" 
                    aria-valuemin="0" 
                    aria-valuemax="100"
                    :style="{width: (quoteCount / maxQuotesNumber) * 100 + '%'}"
                >
                    {{quoteCount}} / {{maxQuotesNumber}}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['quoteCount', 'maxQuotesNumber']
}
</script>

<style>

</style>
