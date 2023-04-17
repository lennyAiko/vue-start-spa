<template>
    <navbar
        :pages="pages"
        :active-page="activePage"
        :nav-link-click="(index => activePage = index)"
    ></navbar>

    <page-viewer
    :page="pages[activePage]"></page-viewer>
</template>

<script>
import PageViewer from './components/PageViewer.vue';
import Navbar from './components/Navbar.vue';

export default {
    components: {
        Navbar,
        PageViewer
    },
    data() {
        return {
            activePage: 0,
            pages: [
                {
                    pageTitle: 'Home Page',
                    content: 'This is home page',
                    link: {text:'Home', url:'index.html'}
                },
                    {
                    pageTitle: 'About Page',
                    content: 'This is about page',
                    link: {text:'About', url:'about.html'},
                },
                {
                    pageTitle: 'Contact Page',
                    content: 'This is contact page',
                    link: {text:'Contact', url:'contact.html'}
                }
            ]
        }
    },
}
</script>