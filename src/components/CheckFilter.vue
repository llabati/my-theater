<template>
    <div :class="{ 'check-filter': true, 'active': checked }" @click="checked = !checked">
        <span class="checkbox"></span>
        <span class="check-filter-title">{{ title }}</span>
    </div>
</template>

<script>
    export default {
        props: [ 'title' ],
        data(){
            return {
                checked: false
            }
        },
        watch: {
            checked(){
                return this.checkFilter()
            }
        },
        methods: {
            checkFilter(){
                this.$emit('check-filter', this.title)
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>