<template>
    <nav :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar', 'navbar-expand-lg']">
        <div class="container-fluid">
            <a href="#" class="navbar-brand">My Vue </a>
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li v-for="(page, index) in pages" class="nav-item" :key="index">
                    <a :href="page.link.url" :title="`This is the ${page.link.text} page`"
                    @click.prevent="navLinkClick(index)" :class="{active: activePage == index}"
                    class="nav-link" aria-current="page">
                    {{ page.link.text }}
                </a>
                </li>
            </ul>
            <form class="d-flex">
                <button class="btn btn-primary"
                @click.prevent="changeTheme()"
                >{{theme}}</button>
            </form>
        </div>
    </nav>
</template>

<script>
export default {
    props: ['pages', 'activePage', 'navLinkClick'],
    data() {
                return {
                    theme: 'light',
                }
            },
    methods: {
        changeTheme() {
            let theme = 'light'

            if (this.theme == 'light') { theme = 'dark' }
            
            this.theme = theme
        }
    }
}
</script>