<template>
    <li>
        <a 
            :href="page.link.url" 
            :title="`This is the ${page.link.text} page`"
            :class="activeClasses"
            class="nav-link" aria-current="page"
            @click.prevent="$bus.$emit('navbarLinkActivated', index)"
        >{{ page.link.text }}</a>
    </li>
    
</template>

<script>
export default {
    props: ['page', 'index', 'isActive'],
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