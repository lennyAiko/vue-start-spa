<template>
    <a 
        :href="page.link.url" 
        :title="`This is the ${page.link.text} page`"
        :class="activeClasses"
        class="nav-link" aria-current="page"
    >{{ page.link.text }}</a>
</template>

<script>
export default {
    props: ['page', 'isActive'],
    computed: {
        activeClasses() {
            return {
                active: this.isActive,
                emphasize: this.isActive
            }
        }
    }
}
</script>

<style scoped>
.emphasize {
    text-decoration: underline !important;
}
</style>