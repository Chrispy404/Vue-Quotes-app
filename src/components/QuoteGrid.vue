<template>
    <div class="row">
		<!-- displaying quotes -->
        <app-quote v-for="(quote, index) in quotes" :key="index" @click.native="deleteQuote(index)">
			{{ quote }}
		</app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue';

    export default {
		//collect quotes from newquote
        props: ['quotes'],
        components: {
            appQuote: Quote
        },
        methods: {
			//emit to app.vue
            deleteQuote(index) {
                this.$emit('quoteDeleted', index);
            }
        }
    }
</script>

<style>

</style>