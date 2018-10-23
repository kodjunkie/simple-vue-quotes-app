<template>
    <div class="row">
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label for="quote">Quote</label>
                <textarea v-model="quote" id="quote" class="form-control" rows="3"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        name: "new-quote",
        data() {
            return {
                quote: ''
            }
        },
        methods: {
            createNew() {
                this.$emit('quotedAdded', this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style scoped>

</style>